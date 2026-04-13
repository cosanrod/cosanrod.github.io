---
title: "Bandit: Nivel 2 -> Nivel 3"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 21-03-2026 — Bandit Level 2

### 🔐 Credenciales

* **Usuario:** `bandit2`
* **Password:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada en un archivo llamado:

```bash
--spaces in this filename--
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

Primero nos conectamos al servidor:

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Listamos los archivos en el directorio:

```bash
ls
```

Salida:

```bash
--spaces in this filename--
```

El nombre del archivo contiene espacios y comienza con `--`, lo cual puede causar problemas al interpretarlo en la terminal.

Para leer su contenido usamos `cat` escapando los espacios con `\`:

```bash
cat ./--spaces\ in\ this\ filename--
```

Salida:

```bash
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

También podemos usar comillas para manejar los espacios:

```bash
cat "./--spaces in this filename--"
```

Salida:

```bash
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

---

### 🧠 Explicación

Este nivel introduce dos problemas comunes en Linux:

* **Espacios en nombres de archivos** → se solucionan usando `\` o comillas `" "`.
* **Nombres que empiezan con `--`** → pueden interpretarse como opciones del comando.

Para evitar conflictos, usamos:

```bash
./
```

Esto indica que el archivo está en el directorio actual y evita que el shell lo interprete como un argumento especial.

---

### 🚩 Flag

```bash
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```
