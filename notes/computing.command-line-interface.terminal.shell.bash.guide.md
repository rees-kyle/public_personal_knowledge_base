---
id: ipe4fyh7bfcta4x3sxxjtjg
title: Guide
desc: ''
updated: 1691594693146
created: 1691041461139
---

<details>
    <summary>sudo</summary>

#
The sudo command is used to execute a command as a superuser or another user, typically with `admin`istrative privileges. It stands for "`superuser do`" and is commonly used to perform tasks that require elevated permissions.

### Syntax
>
`sudo option command`

---
</details>


<details>
    <summary>reboot</summary>

#
To reboot your `system` using Bash, you can use the `reboot` command. However, keep in mind that rebooting your system requires administrative privileges, so you'll typically need to use sudo to execute the command. 

### Input
>
`sudo reboot`

---
</details>


<details>
    <summary>efibootmgr</summary>

#
efibootmgr is a command-line `tool` in Linux that is used `to manage UEFI boot entries`. It allows you to interact with the UEFI firmware on your system, particularly when dealing with boot-related settings. UEFI (Unified Extensible Firmware Interface) is the modern replacement for the traditional BIOS firmware found in computers.

### Input
>
`sudo efibootmgr`

### Output
>
1. BootCurrent: 0000
2. Timeout: 1 seconds
3. BootOrder: 0002,0000,0003,0001
4. Boot0000* ubuntu
5. Boot0001* UEFI:CD/DVD Drive
6. Boot0002* UEFI:Removable Device
7. Boot0003* UEFI:Network Device

---
</details>


<details>
    <summary>change boot order</summary>

### Input
>
`sudo efibootmgr -o` 0002,0000,0003,0001

### Output
>
1. BootCurrent: 0000
2. Timeout: 1 seconds
3. BootOrder: 0000,0001,0002,0003
4. Boot0000* ubuntu
5. Boot0001* UEFI:CD/DVD Drive
6. Boot0002* UEFI:Removable Device
7. Boot0003* UEFI:Network Device

---
</details>


<details>
    <summary>summary</summary>

#
description

### Input
>
input

### Output
>
output

---
</details>