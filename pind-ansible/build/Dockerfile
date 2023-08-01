FROM quay.io/podman/stable

RUN dnf -y update \
    && dnf -y install git gcc python3 python3-pip python3-devel oniguruma-devel --exclude container-selinux \
    && dnf clean all \
    && rm -rf /var/cache /var/log/dnf* /var/log/yum.*;

## Terraform build provides USER => data.coder_workspace.me.owner
ARG USER=coder
ARG EE_IMAGE=quay.io/ansible/creator-ee
RUN groupadd -r ${USER} \
    && useradd -u 998 -m -r -g ${USER} --shell /bin/bash ${USER} \
    && echo -e "${USER}:1:997\n${USER}:1001:64535" > /etc/subuid \
    && echo -e "${USER}:1:997\n${USER}:1001:64535" > /etc/subgid \
	&& echo "${USER} ALL=(ALL) NOPASSWD:ALL" >/etc/sudoers.d/${USER} \
	&& chmod 0440 /etc/sudoers.d/${USER} \
    && echo 'export PATH=$HOME/.local/bin:$PATH' >> /home/${USER}/.bashrc \
    && curl -o /home/${USER}/ansible-navigator.yml https://raw.githubusercontent.com/zjleblanc/coder-templates/master/pind-ansible/build/ansible-navigator.yml \
    && sed -i "s,image:.*,image: ${EE_IMAGE},g" /home/${USER}/ansible-navigator.yml \
    && chown -R ${USER}:${USER} /home/${USER}

USER ${USER}
RUN pip install ansible ansible-navigator ansible-lint --user 
WORKDIR /home/${USER}
