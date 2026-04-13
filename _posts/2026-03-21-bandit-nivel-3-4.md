---
title: "Bandit: Nivel 3 -> Nivel 4"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 21-03-2026 — Bandit Level 3

### 🔐 Credenciales

* **Usuario:** `bandit3`
* **Password:** `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en un archivo oculto dentro del directorio:

```bash id="t0m2dw"
inhere
```

---

### 🧰 Comandos utilizados

```bash 
ls
ls -a
cd
cat
```

---

### 💻 Solución paso a paso

Primero listamos el contenido del directorio home:

```bash id="g2c6cj"
ls
```

Salida:

```bash id="1mrg9q"
inhere
```

Entramos al directorio:

```bash id="w6k8l9"
cd inhere/
```

Listamos su contenido:

```bash id="6lq5z2"
ls
```

Salida:

```bash id="t6u9e1"
(empty)
```

No vemos archivos porque están ocultos. Usamos la opción `-a` para mostrarlos:

```bash id="g3d4kp"
ls -a
```

Salida:

```bash id="i6w2bz"
.  ..  ...Hiding-From-You
```

Finalmente, leemos el archivo oculto:

```bash id="tq2g4m"
cat ...Hiding-From-You
```

Salida:

```bash id="z9y1hv"
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

---

### 🧠 Explicación

En Linux, los archivos que comienzan con `.` son **archivos ocultos**.

El comando:

* `ls` → no muestra archivos ocultos
* `ls -a` → muestra todos los archivos, incluyendo ocultos

Por eso no veíamos el archivo al inicio.

---

### 🚩 Flag

```bash id="j3c7vn"
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
