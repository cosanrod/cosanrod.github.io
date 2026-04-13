---
title: "Bandit: Nivel 1 -> Nivel 2"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 21-03-2026 — Bandit Level 1 -> 2

### 🔐 Credenciales

* **Usuario:** `bandit1`
* **Password:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`
* **Host:** `bandit.labs.overthewire.org`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en un archivo llamado:

```bash
-
```

ubicado en el directorio home.

---

### 🧰 Comandos utilizados

```bash
ls
cat
file
```

---

### 💻 Solución paso a paso

Primero listamos los archivos en el directorio:

```bash
ls
```

Salida:

```bash
-
```

El archivo tiene un nombre poco común (`-`), lo cual puede causar problemas porque este símbolo normalmente se interpreta como una opción en los comandos.

Verificamos el tipo de archivo:

```bash
file ./-
```

Salida:

```bash
./-: ASCII text
```

Finalmente, leemos el contenido del archivo usando:

```bash
cat ./-
```

Salida:

```bash
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---

### 🧠 Explicación

El nombre del archivo (`-`) puede ser interpretado por la terminal como un argumento especial en lugar de un nombre de archivo.

Para evitar esto, usamos:

```bash
./-
```

El `./` indica explícitamente que se trata de un archivo en el directorio actual, evitando confusiones con opciones del comando.

---

### 🚩 Flag

```bash
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---

Si sigues haciendo posts así de limpios, tu blog va a parecer writeups de nivel pro 👀
Si quieres, en el siguiente te ayudo a hacerlo aún más “hacker aesthetic” 😏
