FROM {{ cookiecutter.image_name }}:latest

ARG USER_ID
ARG GROUP_ID
ARG USER_NAME
ARG GROUP_NAME

RUN echo "--- INIT ---" \
#
# User / Group ID
&&  useradd -s /bin/bash -m ${USER_NAME} \
&&  export HOME=/home/${USER_NAME} \
&&  usermod -u ${USER_ID} ${USER_NAME} \
&&  groupadd -g ${GROUP_ID} ${GROUP_NAME} \
&&  usermod -g ${GROUP_NAME} ${USER_NAME} \
&&  chown -R ${USER_ID}:${GROUP_ID} /home/${USER_NAME} \
#
# Git
&&  git config --global user.email {{ cookiecutter.git_email }} \
&&  git config --global user.name {{ cookiecutter.git_user }} \
#
&&  echo "--- FIN ---"