FROM archlinux/archlinux:base
LABEL author="sinuhe.dev@gmail.com"

RUN echo [multilib] >> /etc/pacman.conf
RUN echo Include = /etc/pacman.d/mirrorlist >> /etc/pacman.conf

RUN pacman -Syy --noconfirm

RUN pacman -S --noconfirm adwaita-icon-theme lutris wine winetricks
RUN pacman -S --noconfirm nvidia nvidia-utils nvidia-settings vulkan-icd-loader vulkan-intel lib32-nvidia-utils lib32-mesa lib32-vulkan-icd-loader lib32-vulkan-intel

ENV GTK_THEME=Adwaita:dark

CMD lutris
