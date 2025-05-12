# vps-me

```
sudo apt update
sudo apt install docker.io docker-compose
sudo docker-compose -f win10.yml up
```



```
sudo apt update && sudo apt install qemu-system -y
qemu-img create -f raw /home/user/Android/Sdk/disk.img 160G
sudo apt update && sudo apt upgrade -y && sudo apt install cpulimit qemu-system swtpm -y
wget https://raw.githubusercontent.com/clearlinux/common/refs/heads/master/OVMF_VARS.fd && wget https://raw.githubusercontent.com/clearlinux/common/refs/heads/master/OVMF_CODE.fd

xhost + ; mkdir /tmp/mytpm1
swtpm socket \
    --tpmstate dir=/tmp/mytpm1 \
    --ctrl type=unixio,path=/tmp/mytpm1/swtpm-sock \
    --log level=10 &
sudo kvm -cpu host,+topoext,hv_relaxed,hv_spinlocks=0x1fff,hv-passthrough,+pae,+nx,kvm=on,+svm,+vme,+avx2,+vmx,+hypervisor,+xsave -smp sockets=1,cores=16,threads=1 -M q35,usb=on -device usb-tablet -m 50G     -device virtio-balloon-pci -vga virtio -net nic,netdev=n0,model=virtio-net-pci -netdev user,id=n0,hostfwd=tcp::3389-:3389 -boot d     -device virtio-serial-pci -device virtio-rng-pci      -chardev socket,id=chrtpm,path=/tmp/mytpm1/swtpm-sock -tpmdev emulator,id=tpm0,chardev=chrtpm -device tpm-tis,tpmdev=tpm0 -enable-kvm -device nvme,serial=deadbeef,drive=nvm -drive file=/home/user/Android/Sdk/disk.img,if=none,id=nvm -drive file=/home/user/Downloads/win.iso,media=cdrom -drive file=/home/user/Downloads/virtio.iso,media=cdrom -drive file=OVMF_CODE.fd,format=raw,if=pflash     -drive file=OVMF_VARS.fd,format=raw,if=pflash     -uuid e47ddb84-fb4d-46f9-b531-14bb15156336
```

```
Chọn win11 pro
Shift F10
oobe/bypassnro
```

```
Cài đặt mang Virtio
Bật remote desktop
Tải radmin
Quan trong: tắt sleep -> never
```
