# Requisitos Previos

Para desplegar este servicio necesitas cumplir los siguientes requisitos.

## 1. Sistema Operativo

Debes tener Windows 10 (versión 1809 o superior) o Windows Server 2019/2022.

## 2. Privilegios

Es obligatorio ejecutar la terminal como **Administrador**.

![Captura de PowerShell](img/powershell.png)

## 3. Instalación del Servicio

Ejecuta este comando en PowerShell para comprobar si ya lo tienes instalado:

```powershell
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH.Server*'
```
