# Error-VT-x

En ocasiones al utilizar Virtualbox u otro programa de virtualización en W10 se da un error al iniciar una VM.

En la mayoría de ocasiones puede no estar habilitada la virtualización, varias formas de comprobarlo son:

- ctrl+alt+supr, seleccionar "Administrador de tareas" y en la pestaña rendimiento aparece, por ejemplo, "Virtualización : deshabilitado" 
- Por linea de comandos con systeminfo.exe (mirar las lineas finales)

SOLUCIÓN: Entrar en la BIOS, F10 para seleccionar las configuraciones y habilitar la virtualización.

En la algunas ocasiones debido a que Docker puede correr en Hyper-v se puede dar este error:

- SOLUCIÓN1: Panel de control, programas, características de windows y aqui quitar (si aparecen seleccionadas) hyper-v y contenedores.
- Mediante Windows Powershell ejecutado en administrador 
  > bcdedit
  habilitado si hypervisorlaunchtype Auto
  SOLUCIÓN2: > bcdedit /set hypervisorlaunchtype off
  la linea anterior lo pone a off, es decir, se deshabilita
