---
title: "Bandit: Nivel 7 -> Nivel 8"
date: 2026-03-26 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 26-03-2026 — Bandit Level 7

### 🔐 Credenciales

* **Usuario:** `bandit7`
* **Password:** `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en el archivo:

```bash id="x7m2qa"
data.txt
```

junto a la palabra:

```bash id="k9p4vd"
millionth
```

---

### 🧰 Comandos utilizados

```bash id="v3n8cx"
ls
grep
```

---

### 💻 Solución paso a paso

Primero listamos los archivos en el directorio:

```bash id="q1w6zr"
ls
```

Salida:

```bash id="y8k2lm"
data.txt
```

Buscamos la palabra clave dentro del archivo usando `grep`:

```bash id="m4c9px"
grep millionth data.txt
```

Salida:

```bash id="z2v7hs"
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

---

### 🧠 Explicación

El comando `grep` permite buscar texto dentro de archivos.

En este caso:

* `grep millionth data.txt` → busca la línea que contiene la palabra *millionth*
* La contraseña se encuentra en la misma línea, justo después de esa palabra

---

### 🚩 Flag

```bash id="p6t3qn"
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
