# virt-manager
## Installation
### Arch
```
sudo pacman -S virt-manager qemu libvirt dnsmasq
```
```
sudo systemctl enable libvirtd.service
```
```
sudo systemctl start libvirtd.service
```
```
sudo virsh net-start default
```
```
sudo usermod -aG libvirt $(whoami)
```
## Enable send file and copy paste feature
### Arch
```
sudo pacman -S spice-vdagent
```
```
sudo systemctl start spice-vdagentd
```
```
sudo systemctl enable spice-vdagentd
```
## Auto resize screen resolution
Note: may need spice-vdagent, gnome to work

View -> Scale display -> Always, Auto resize VM with window
## GPU Passthrough
### Video
Model: Virtio

3D accel: enable

### Display
Type: Spice Server

Listen Type: None

OpenGL: enable

## Use without root privilage (not secure)
Warning! normal user can acces vm

QEMU requires root privilege by default due to connection QEMU/KVM storage pool is in root. Add QEMU/KVM user session and delete the default connection. Now images are created in home directory instead of root.
