# bluetooth-5.13 - TP-LINK UB500

- Secure Boot needs to be disabled, check ``mokutil --sb-state``

## Build

- Build

```
sudo apt install git dkms
git clone https://github.com/jeremyb31/bluetooth-5.13.git
cd bluetooth-5.13
make
sudo mv /lib/modules/$(uname -r)/kernel/drivers/bluetooth/btusb.ko /lib/modules/$(uname -r)/kernel/drivers/bluetooth/btusb.ko.bak
sudo cp btusb.ko /lib/modules/$(uname -r)/kernel/drivers/bluetooth/
sudo depmod -a
```

- Reboot or reload ``btusb``

```
sudo modprobe -r btusb
sudo modprobe -v btusb
```
