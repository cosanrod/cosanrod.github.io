---

title: "Bandit: Nivel 0 -> Nivel 1"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 21-03-2026 — Bandit Level 0

### 🔐 Credenciales

* **Usuario:** `bandit0`
* **Password:** `bandit0`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en un archivo llamado:

```bash
readme
```

ubicado en el directorio home.

---

### 🧰 Comandos utilizados

```bash
ls
cat
```

---

### 💻 Solución paso a paso

Primero listamos los archivos en el directorio:

```bash
ls
```

Salida:

```bash
readme
```

Luego, leemos el contenido del archivo:

```bash
cat readme
```

Salida:

```bash
Congratulations on your first steps into the bandit game!!
[...]
The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

---

### 🧠 Explicación

El archivo `readme` contiene directamente la contraseña del siguiente nivel.
Para obtenerla, simplemente utilizamos:

* `ls` para listar los archivos del directorio.
* `cat` para visualizar el contenido del archivo.

Este nivel introduce comandos básicos de navegación y lectura de archivos en Linux.

---

### 🚩 Flag

```bash
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```
