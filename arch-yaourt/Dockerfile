FROM base/archlinux

USER root
ADD mirrorlist /etc/pacman.d/mirrorlist
RUN pacman --noconfirm -Syyu && \
    pacman --noconfirm -S base-devel git && \
    yes | pacman -Scc && \
    groupadd --system sudo && \
    useradd -m -G sudo user && \
    sed -i -e "s/Defaults    requiretty.*/ #Defaults    requiretty/g" /etc/sudoers && \
    echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER user
RUN cd /home/user && \
    git clone --depth 1 https://aur.archlinux.org/package-query.git && \
    git clone --depth 1 https://aur.archlinux.org/yaourt.git && \
    cd ~/package-query && \
    echo start makepkg package-query && \
    makepkg -s -i --noconfirm && \
    cd ~/yaourt && \
    makepkg -s -i --noconfirm && \
    rm -rf ~/package-query ~/yaourt
USER root

