# https://cloud-images.ubuntu.com/
# cloud-localds -m local seed.img my-user-data

launch:
	qemu-system-x86_64  \
	-machine accel=kvm,type=q35 \
	-cpu host \
	-m 2G \
	-nographic \
	-device virtio-net-pci,netdev=net0 \
	-netdev user,id=net0,hostfwd=tcp::2222-:22 \
	-drive if=virtio,format=qcow2,file=hdd.img \
	-drive if=virtio,format=raw,file=seed.img \
	-kernel /home/user/repos/linux/arch/x86/boot/bzImage -append "console=ttyS0 root=/dev/vda1"
