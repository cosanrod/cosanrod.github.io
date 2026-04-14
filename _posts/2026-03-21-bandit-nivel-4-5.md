---
title: "Bandit: Nivel 4 -> Nivel 5"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 21-03-2026 — Bandit Level 4

### 🔐 Credenciales

* **Usuario:** `bandit4`
* **Password:** `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en el **único archivo legible por humanos** dentro del directorio:

```bash id="o3gk1n"
inhere
```

---

### 🧰 Comandos utilizados

```bash id="d8x2pa"
ls
cd
file
cat
```

---

### 💻 Solución paso a paso

Primero listamos el contenido del directorio home:

```bash id="l5u1hz"
ls
```

Salida:

```bash id="9qg7bm"
inhere
```

Entramos al directorio:

```bash id="1w0ncs"
cd inhere/
```

Listamos los archivos:

```bash id="yq3k8r"
ls
```

Salida:

```bash id="n7x4vd"
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
```

Hay varios archivos, pero no sabemos cuál contiene texto legible.
Usamos el comando `file` con un comodín para analizar todos:

```bash id="b2k6zw"
file ./*
```

Salida:

```bash id="j8c9lx"
./-file00: data
./-file01: OpenPGP Public Key
./-file02: OpenPGP Public Key
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```

El único archivo con texto legible es:

```bash id="z4v9hs"
./-file07
```

Leemos su contenido:

```bash id="x2f7ke"
cat ./-file07
```

Salida:

```bash id="m8p1qy"
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

---

### 🧠 Explicación

En este nivel hay múltiples archivos, pero solo uno contiene texto legible.

* `file` → permite identificar el tipo de contenido de un archivo
* `./*` → es un comodín que selecciona todos los archivos del directorio

Buscamos específicamente el que diga **ASCII text**, ya que indica que es legible por humanos.

Además, usamos `./` porque los nombres de los archivos comienzan con `-`, lo que podría causar conflictos con las opciones de los comandos.

---

### 🚩 Flag

```bash id="r6t2wd"
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```
