# Configuración en Windows

El archivo de configuración de SSH en Windows **no** está en `/etc/ssh`, sino en una carpeta oculta llamada `ProgramData`.

## 1. Ubicación del archivo

La ruta absoluta es:
`C:\ProgramData\ssh\sshd_config`

!!! warning "Copia de Seguridad"
Antes de editar, haz un backup con este comando:
`Copy-Item C:\ProgramData\ssh\sshd_config C:\ProgramData\ssh\sshd_config.bak`

## 2. Edición de Parámetros

Puedes editar el archivo usando el **Bloc de Notas** desde la terminal:

```powershell
notepad C:\ProgramData\ssh\sshd_config

Parámetro,Valor,Explicación
Port,2222,Cambiamos el puerto por defecto.
MaxAuthTries,3,Evitar fuerza bruta.
PasswordAuthentication,yes,(Opcional) Cambiar a 'no' si usas claves.
```
