FROM rockylinux:9

ARG USERNAME=codespace
ARG USER_UID=1000
ARG USER_GID=$USER_UID
ARG HOMEDIR=/home/$USERNAME

# set user to root to install packages
USER root

# create groupid
RUN groupadd --gid ${USER_GID} ${USERNAME}

# Create a non-root user to use if preferred 
RUN useradd -u ${USER_UID} -g ${USER_GID} -d ${HOMEDIR} ${USERNAME}

# Update DNF
RUN dnf -y update

# groupinstall development tools 
RUN dnf -y groupinstall development
