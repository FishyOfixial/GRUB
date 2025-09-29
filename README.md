# Lab 1.4: GRUB Configuration and Boot Process Analysis

**Student:** Ivan Ramos de la Torre  
**Date:** 28/09/2025  
**Course:** Operating Systems  

---

## Executive Summary
En este laboratorio se analizó la configuración actual de **GRUB2**, el gestor de arranque más común en Linux.  
Se realizaron cambios en el archivo de configuración principal, como aumentar el tiempo de espera del menú de arranque de 5 a 30 segundos y forzar la visualización del menú. Posteriormente se regeneró la configuración y se verificó que el sistema continuara arrancando de manera normal.  
Además, se investigaron procedimientos de recuperación ante fallos del gestor de arranque.  

Los resultados mostraron que las modificaciones se aplicaron correctamente y el sistema pudo reiniciar sin inconvenientes, reforzando la comprensión de la estructura y funcionamiento de GRUB2.  

---

## Objectives Completed
- Analizar la estructura y funcionalidad del bootloader GRUB2.  
- Modificar configuraciones de GRUB de manera segura en una VM.  
- Implementar cambios en el comportamiento del menú de arranque.  
- Investigar y documentar procedimientos de recuperación de GRUB.  
- Aplicar buenas prácticas de seguridad en configuraciones críticas.  

---

## Main Changes Implemented
1. **Respaldos creados**  
   - `/etc/default/grub.backup`  
   - `/boot/grub/grub.cfg.backup`  

2. **Modificaciones en `/etc/default/grub`:**
   ```bash
   GRUB_DEFAULT=0
   GRUB_TIMEOUT=30
   GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
   GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
   GRUB_CMDLINE_LINUX=""
   GRUB_TIMEOUT_STYLE=menu
