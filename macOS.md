一、设置macOS虚拟机

1.增加CDROM  opencore-osx-proxmox-vm.iso

2.cd /etc/pve/qemu-server

3.cp 102.conf 102.conf.bak

4.sed  -i 's/media=cdrom/cache=unsafe/g' 102.conf

二、增加永久路由

# 察看网络接口
sudo networksetup -listallnetworkservices

#  Add Route via Cable
sudo networksetup -setadditionalroutes 'Apple USB Ethernet Adapter' 192.168.88.0 255.255.255.0 192.168.10.1 10.73.192.192 255.255.255.192 192.168.10.1 10.73.192.168 255.255.255.255 192.168.10.1

# Add Route via Wi-Fi
sudo networksetup -setadditionalroutes Wi-Fi 192.168.80.0 255.255.255.0 192.168.1.5 192.168.88.0 255.255.255.0 192.168.1.5 10.73.192.192 255.255.255.248 192.168.1.5

# 临时增加路由
sudo route -n add -net 192.168.10.192/28 10.73.192.194
