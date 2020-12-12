# Liunx

## 一、linux内核相关
### 1.1 多内核安装

[Linux内核地址](https://kernel.ubuntu.com/~kernel-ppa/mainline/)
找到对应版本的内核下载对应的内核.deb文件
```shell
dpkg -i *.deb
```
### 1.2 内核默认启动切换
1. grub 存在于/boot/grub/grub.cfg
2. 修改grub配置

set default="0"：表示默认的启动项，“0”表示第一个，依次类推。
set timeout=10：表示默认等待时间，单位是秒。

找到对应内核启动项，剪切复制到所有Ubuntu启动项之前，例如：
```v
	menuentry 'Ubuntu，Linux 5.4.0-58-generic' --class ubuntu --class gnu-linux --class gnu --class os $menuentry_id_option 'gnulinux-5.4.0-58-generic-advanced-4affe37c-45be-43fb-b997-0c6e21a04a44' {
		recordfail
		load_video
		gfxmode $linux_gfx_mode
		insmod gzio
		if [ x$grub_platform = xxen ]; then insmod xzio; insmod lzopio; fi
		insmod part_msdos
		insmod ext2
		set root='hd0,msdos8'
		if [ x$feature_platform_search_hint = xy ]; then
		  search --no-floppy --fs-uuid --set=root --hint-bios=hd0,msdos8 --hint-efi=hd0,msdos8 --hint-baremetal=ahci0,msdos8  4affe37c-45be-43fb-b997-0c6e21a04a44
		else
		  search --no-floppy --fs-uuid --set=root 4affe37c-45be-43fb-b997-0c6e21a04a44
		fi
		echo	'载入 Linux 5.4.0-58-generic ...'
	        linux	/boot/vmlinuz-5.4.0-58-generic root=UUID=4affe37c-45be-43fb-b997-0c6e21a04a44 ro  quiet splash $vt_handoff
		echo	'载入初始化内存盘...'
		initrd	/boot/initrd.img-5.4.0-58-generic
	}
```
3. 保存并退出。
最后，重新启动机器，一切将变得如你所愿。