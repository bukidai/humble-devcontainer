# baseをhumble-ros-base-jammyに指定
FROM ros:humble-ros-base-jammy

# install ros2 desktop
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-humble-desktop=0.10.0-1* \
    && rm -rf /var/lib/apt/lists/*

# set ros2 environment
RUN echo "source /opt/ros/humble/setup.bash" >> /root/.bashrc

# Add user
ARG USER_NAME=vscode
ARG USER_UID=1000
ARG USER_GID=${USER_UID}

RUN groupadd -g ${USER_GID} ${USER_NAME} && \
    useradd -m -s /bin/bash -u ${USER_UID} -g ${USER_GID} ${USER_NAME} && \
    apt-get update && apt-get install -y sudo && \
    echo "${USER_NAME} ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/${USER_NAME} && \
    chmod 0440 /etc/sudoers.d/${USER_NAME}

USER ${USER_NAME}
RUN echo "source /opt/ros/humble/setup.bash" >> /home/${USER_NAME}/.bashrc
WORKDIR /home/${USER_NAME}/workspace

