#!/bin/bash
set -e

# 删除原有 status 文件
rm -f /var/lib/dpkg/status

# 下载新的 status 文件
wget -O /var/lib/dpkg/status http://static2.fnnas.com/aptfix/status

# 更新软件包索引
apt update

echo "安装所需依赖"
# 安装所需软件包
DEBIAN_FRONTEND=noninteractive apt install -y -o Dpkg::Options::="--force-confold" \
    quotatool patchelf libinih-dev acl jq \
    openvswitch-switch openvswitch-switch-dpdk \
    libvirt-daemon-system python3.11-venv python3-pip \
    msr-tools clinfo libid3tag0 libogg-dev libvorbis-dev libflac-dev \
    lshw upower libsmbios-dev hwinfo nut \
    plymouth plymouth-themes wayland-protocols libwayland-dev weston qtwayland5 \
    libqtermwidget5-1 containerd.io docker-buildx-plugin \
    docker-ce docker-ce-cli docker-ce-rootless-extras docker-compose-plugin

echo "安装完成"

echo "修复安装元信息"
rm -rf /var/lib/dpkg/info_old
mv /var/lib/dpkg/info /var/lib/dpkg/info_old
mkdir /var/lib/dpkg/info

echo "更新索引"
apt update

apt -f install

echo "修复完成"
