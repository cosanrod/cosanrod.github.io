---
title: "Bandit: Nivel 5 -> Nivel 6"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 21-03-2026 — Bandit Level 5

### 🔐 Credenciales

* **Usuario:** `bandit5`
* **Password:** `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en algún archivo dentro del directorio:

```bash id="m1k9zp"
inhere
```

El archivo cumple con las siguientes condiciones:

* Es **legible por humanos**
* Tiene un tamaño de **1033 bytes**
* **No es ejecutable**

---

### 🧰 Comandos utilizados

```bash id="d3x8jq"
ls
cd
find
file
grep
cat
```

---

### 💻 Solución paso a paso

Primero listamos el contenido del directorio home:

```bash id="q8n2ly"
ls
```

Salida:

```bash id="c4v7tw"
inhere
```

Entramos al directorio:

```bash id="b6r1xa"
cd inhere/
```

Listamos las carpetas disponibles:

```bash id="z2y5mn"
ls
```

Salida:

```bash id="k9p3ld"
maybehere00  maybehere01  maybehere02  maybehere03  maybehere04  
maybehere05  maybehere06  maybehere07  maybehere08  maybehere09  
maybehere10  maybehere11  maybehere12  maybehere13  maybehere14  
maybehere15  maybehere16  maybehere17  maybehere18  maybehere19
```

Debido a la gran cantidad de archivos, utilizamos `find` para filtrar los que cumplen las condiciones:

```bash id="h7x4qe"
find . -type f -size 1033c ! -executable -exec file {} + | grep "ASCII text"
```

Salida:

```bash id="w1c8os"
./maybehere07/.file2: ASCII text, with very long lines (1000)
```

Leemos el archivo encontrado:

```bash id="v3m9rb"
cat maybehere07/.file2
```

Salida:

```bash id="x5p2kf"
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

---

### 🧠 Explicación

Este nivel introduce el uso de `find` para búsquedas avanzadas:

* `find .` → busca en el directorio actual y subdirectorios
* `-type f` → solo archivos
* `-size 1033c` → archivos de exactamente 1033 bytes
* `! -executable` → excluye archivos ejecutables
* `-exec file {} +` → analiza el tipo de archivo
* `| grep "ASCII text"` → filtra solo texto legible

Con esto reducimos cientos de archivos a uno solo.

---

### 🚩 Flag

```bash id="n8z6vu"
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```
