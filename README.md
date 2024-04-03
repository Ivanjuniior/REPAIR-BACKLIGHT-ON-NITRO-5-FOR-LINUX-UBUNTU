# REPAIR-BACKLIGHT-ON-NITRO-5-FOR-LINUX-UBUNTU

1 - Rode sudo dmesg | grep -i secure, se aparecer algo como Secure boot enabled então o secure boot esta habilitado, se uma das saídas forem Secure boot disabled Secure boot está desabilitado.
2 - mokutil --sb-state
3 - bootctl status

Se estiver com o secure boot habilitado, tente iniciar com ele desablitado (entre em sua BIOS no boot, e desabilite-o), e veja se o problema persiste.

Qual a saída do seguinte comando: lspci -k | grep -A 2 -E "(VGA|3D)"

Se no modulo referente a Nvidia estiver como Kernel drive in use: nvidia, tente iniciar seu sistema com a opção acpi_backlight=native


sudo nano /etc/default/grub

GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi_backlight=native
