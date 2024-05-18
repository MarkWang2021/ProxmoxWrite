增加CDROM  opencore-osx-proxmox-vm.iso

cd /etc/pve/qemu-server

cp 102.conf 102.conf.bak

sed  -i 's/media=cdrom/cache=unsafe/g' 102.conf
