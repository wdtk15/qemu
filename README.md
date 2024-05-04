```
wget -O garuda-dr460nized-linux-zen-240428.iso "https://kumisystems.dl.sourceforge.net/project/garuda-linux/garuda/dr460nized/240428/garuda-dr460nized-linux-zen-240428.iso?viasf=1"
```
```
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
```
```
tar -xf ngrok-v3-stable-linux-amd64.tgz
```
```
rm -rf ngrok-v3-stable-linux-amd64.tgz
```
```
./ngrok config add-authtoken 2fz8d4WXRykwxMi4bdSpafbzKfC_7buhpHyQ1c15zDzyGYagT
```
```
./ngrok tcp 5900
```
```
sudo apt update && sudo apt upgrade && sudo apt install qemu-kvm
```
```
sudo qemu-img create -f raw 1.img 64G
```
```
sudo qemu-system-x86_64 -m 8G -cpu host -boot order=c -drive file=garuda-dr460nized-linux-zen-240428.iso,media=cdrom -drive file=1.img,format=raw -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=2 -device rtl8139,netdev=n0 -netdev user,id=n0 -vga qxl -enable-kvm
```
```
rm -rf garuda-dr460nized-linux-zen-240428.iso
```
```
sudo qemu-system-x86_64 -m 8G -cpu host -boot order=c -drive file=1.img,format=raw -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=2 -device rtl8139,netdev=n0 -netdev user,id=n0 -vga qxl -enable-kvm
```
