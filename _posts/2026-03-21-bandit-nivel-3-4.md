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

```bash
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

```bash 
ls
```

Salida:

```bash 
inhere
```

Entramos al directorio:

```bash 
cd inhere/
```

Listamos su contenido:

```bash 
ls
```

Salida:

```bash 
(empty)
```

No vemos archivos porque están ocultos. Usamos la opción `-a` para mostrarlos:

```bash 
ls -a
```

Salida:

```bash 
.  ..  ...Hiding-From-You
```

Finalmente, leemos el archivo oculto:

```bash
cat ...Hiding-From-You
```

Salida:

```bash 
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

```bash 
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
