FROM registry.access.redhat.com/ubi9:9.4-947.1714667021 AS ubi-micro-build
RUN mkdir -p /mnt/rootfs
RUN dnf list installed > /mnt/rootfs/befor.txt
RUN dnf install --installroot /mnt/rootfs libstdc++ --releasever 9 --setopt install_weak_deps=false --nodocs -y >> /mnt/rootfs/install.log && \
    dnf --installroot /mnt/rootfs clean all >> /mnt/rootfs/install.log && \
    rpm --root /mnt/rootfs -e --nodeps setup >> /mnt/rootfs/install.log 
RUN dnf list installed > /mnt/rootfs/after.txt
