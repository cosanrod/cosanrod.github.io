---
title: "Bandit: Nivel 6 -> Nivel 7"
date: 2026-03-21 12:00:00 -0600
categories: [OverTheWire, Bandit]
tags: [linux, ctf, basico]
---

## 🗓️ 21-03-2026 — Bandit Level 6

### 🔐 Credenciales

* **Usuario:** `bandit6`
* **Password:** `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`
* **Host:** `bandit.labs.overthewire.org`
* **Puerto:** `2220`

---

### 🎯 Objetivo

Encontrar la contraseña del siguiente nivel.
La contraseña está almacenada **en algún lugar del servidor** y cumple con:

* Pertenece al usuario `bandit7`
* Pertenece al grupo `bandit6`
* Tiene un tamaño de **33 bytes**

---

### 🧰 Comandos utilizados

```bash id="z8m4yx"
ls
find
cat
```

---

### 💻 Solución paso a paso

Primero listamos el contenido del directorio home:

```bash id="m2q7vc"
ls -a
```

Salida:

```bash id="r9w1pk"
.  ..  .bash_logout  .bashrc  .profile
```

No hay nada útil, así que debemos buscar en **todo el sistema**.

Utilizamos `find` desde la raíz (`/`) aplicando los filtros dados:

```bash id="x6k3ld"
find / -size 33c -user bandit7 -group bandit6 2>/dev/null
```

Salida:

```bash id="p4n8zs"
/var/lib/dpkg/info/bandit7.password
```

Leemos el contenido del archivo:

```bash id="t7v2bj"
cat /var/lib/dpkg/info/bandit7.password
```

Salida:

```bash id="y5c9ha"
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

---

### 🧠 Explicación

En este nivel usamos `find` a nivel global:

* `find /` → busca en todo el sistema
* `-size 33c` → archivos de 33 bytes
* `-user bandit7` → propiedad del usuario bandit7
* `-group bandit6` → propiedad del grupo bandit6

El parámetro clave:

```bash id="n1f6qd"
2>/dev/null
```

* Redirige los errores (como *Permission denied*)
* Evita que la salida se llene de ruido

---

### 🚩 Flag

```bash id="k3u8rx"
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
