---
title: "Bandit: Nivel 8 -> Nivel 9"
date: 2026-03-26 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 26-03-2026 — Bandit Level 8

### 🔐 Credenciales

* **Usuario:** `bandit8`
* **Password:** `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en el archivo:

```bash id="m2x9kp"
data.txt
```

y es la **única línea que aparece una sola vez** en todo el archivo.

---

### 🧰 Comandos utilizados

```bash id="z7v3qn"
ls
sort
uniq
```

---

### 💻 Solución paso a paso

Primero listamos los archivos:

```bash id="p4c8yr"
ls
```

Salida:

```bash id="k9d2lm"
data.txt
```

Para encontrar la línea única usamos una combinación de comandos:

```bash id="t6n1xw"
sort data.txt | uniq -u
```

Salida:

```bash id="w3q8zs"
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

---

### 🧠 Explicación

Este nivel introduce el uso de **pipes (`|`)** para combinar comandos:

* `sort` → ordena el contenido del archivo
* `uniq` → filtra líneas repetidas

⚠️ **¿Por qué es necesario usar `sort`?**

El comando `uniq` **solo detecta duplicados cuando están uno junto al otro**.
Si el archivo no está ordenado, las líneas repetidas pueden estar separadas y `uniq` no las detectará correctamente.

👉 Ejemplo:

```bash id="h4x2pz"
a
b
a
```

Si usamos `uniq` directamente, no elimina duplicados porque no están consecutivos.

Pero después de usar `sort`:

```bash id="v9k3qn"
a
a
b
```

Ahora sí, `uniq` puede identificar correctamente las repeticiones.

---

### 🚩 Flag

```bash id="x8r2mv"
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
