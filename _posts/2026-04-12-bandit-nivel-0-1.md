---
title: "Bandit: Nivel 0 -> Nivel 1"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## Objetivo del Reto
La contraseña para el siguiente nivel está almacenada en un archivo llamado `readme` dentro del directorio personal (*home*). Debemos obtenerla para conectarnos al usuario `bandit1` mediante SSH.

## Datos de Conexión
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`
* **Usuario:** `bandit0`
* **Contraseña:** `bandit0`

---

## Solución

Una vez conectados al servidor, realizamos los siguientes pasos para encontrar la bandera:

### 1. Enumeración de archivos
Primero, listamos el contenido del directorio para confirmar la ubicación del archivo `readme`:

```bash
bandit0@bandit:~$ ls
readme
```

### 2. Lectura del contenido
Utilizamos el comando cat (concatenate) para mostrar el texto almacenado en el archivo:

```bash
bandit0@bandit:~$ cat readme
```
### Resultado de la ejecución:

```bash
Congratulations on your first steps into the bandit game!!
[...]
The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

### Resumen Técnico
ls: Utilizado para listar archivos y directorios.
cat: Utilizado para leer y mostrar el contenido de archivos de texto en la terminal.

### Flag
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If


