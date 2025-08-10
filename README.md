# PinguSSH

Un script en Bash que realiza un ataque de diccionario (con opción de generar variaciones) para intentar **descifrar la contraseña de una clave privada SSH** protegida.  
Ideal para auditorías de seguridad, recuperación de contraseñas olvidadas o pruebas de robustez.

---

### 📦 Características

- ✅ Soporte para Linux y macOS
- 🎨 Salida colorida y banner ASCII personalizable
- 🔁 Generador de variaciones de contraseñas
- 📊 Estadísticas detalladas al final de la ejecución
- 🚦 Soporte para niveles de verbosidad
- 🛑 Manejo de interrupciones (Ctrl+C) con resumen limpio

---

### 🖥️ Requisitos

- `ssh-keygen` (incluido en OpenSSH)
- Bash 4.x o superior

---

### ⚙️ Instalación

```bash
git clone https://github.com/santitub/pinguzip.git
cd ssh-key-password-cracker
chmod +x pingussh.sh
````

---

### 🚀 Uso

```bash
./pingussh.sh [-v | -vv] id_rsa wordlist.txt
```

#### 📌 Parámetros

| Parámetro      | Descripción                                                     |
| -------------- | --------------------------------------------------------------- |
| `-v`           | Modo verboso: muestra progreso general                          |
| `-vv`          | Modo muy verboso: muestra cada intento de contraseña            |
| `id_rsa`       | Ruta a tu archivo de clave SSH privada protegido por contraseña |
| `wordlist.txt` | Diccionario con posibles contraseñas (una por línea)            |

---

### 🔄 Variaciones de contraseñas (opcional)

Al iniciar el script, se preguntará:

> ❓ ¿Deseas probar variaciones de contraseñas? (s/n)

Si aceptas, por cada contraseña se probarán versiones como:

* `password123`
* `password!`
* `abcpassword`
* `PASSWORD` (mayúsculas)
* `password` (minúsculas)

Esto **aumenta las probabilidades de éxito**, especialmente con contraseñas simples o predecibles.

---

### 📈 Ejemplo de ejecución

```bash
./pingussh.sh -v ~/.ssh/id_rsa rockyou.txt
```

### ⚠️ Aviso legal

> 🛑 **Este script está destinado únicamente a fines educativos o de recuperación/autoevaluación.**
> **No lo utilices en sistemas o claves que no te pertenecen.** El uso indebido puede ser ilegal y está sujeto a sanciones.

### 🙌 Créditos

Desarrollado con ❤️ por **Santitub**
