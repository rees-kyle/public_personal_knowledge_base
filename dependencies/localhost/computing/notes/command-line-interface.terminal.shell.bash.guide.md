---
id: ipe4fyh7bfcta4x3sxxjtjg
title: Guide
desc: ''
updated: 1692457827059
created: 1691041461139
---

<!-- start of 'sudo' section -->
<details>
    <summary>sudo</summary>

#
The sudo command is used to execute a command as a superuser or another user, typically with `admin`istrative privileges. It stands for "`superuser do`" and is commonly used to perform tasks that require elevated permissions.

### syntax
>
`sudo option command`

---
</details>
<!-- end of 'sudo' section -->



<!-- start of 'reboot' section -->
<details>
    <summary>reboot</summary>

#
to reboot your `system` using Bash, you can use the `reboot` command. However, keep in mind that rebooting your system requires administrative privileges, so you'll typically need to use sudo to execute the command. 

### input
>
`sudo reboot`

---
</details>
<!-- end of 'reboot' section -->



<!-- start of 'efibootmgr' section -->
<details>
    <summary>efibootmgr</summary>

#
efibootmgr is a command-line `tool` in Linux that is used `to manage UEFI boot entries`. It allows you to interact with the UEFI firmware on your system, particularly when dealing with boot-related settings. UEFI (Unified Extensible Firmware Interface) is the modern replacement for the traditional BIOS firmware found in computers.

### input
>
`sudo efibootmgr`

### output
>
screenshot

---
</details>
<!-- end of 'efibootmgr' section -->



<!-- start of 'change boot order' section -->
<details>
    <summary>change boot order</summary>

### input
>
`sudo efibootmgr -o` 0002,0000,0003,0001

### output
>
screenshot

---
</details>
<!-- end of 'change boot order' section -->



<!-- start of 'example' section -->
<details>
    <summary>example</summary>

#
description

### input
>
input

### output
>
output

---
</details>
<!-- end of 'example' section -->