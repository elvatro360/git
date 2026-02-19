# 📚 Git - Control de Versiones (Guía Mejorada)

## 🚀 FLUJO DE TRABAJO BÁSICO

**Pasos que debes hacer cada vez que termines de trabajar:**

```bash
git status          # Ver qué cambió
git add .           # Preparar todos los cambios
git commit -m "Descripción clara del cambio"  # Guardar cambios
git push            # Subir a GitHub
```

---

## ⚙️ CONFIGURACIÓN INICIAL (Una sola vez)

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

---

## 📋 TODOS LOS COMANDOS ORGANIZADOS

### 📁 Crear y Clonar Repositorios
| Comando | Qué hace |
|---------|----------|
| `git init` | Inicia un repositorio en tu PC |
| `git clone <URL>` | Descarga un repositorio desde GitHub |
| `git remote add origin <URL>` | Conecta tu repo local a GitHub |

### 📝 Agregar y Confirmar Cambios (El workflow principal)
| Comando | Qué hace |
|---------|----------|
| `git status` | Ver estado (WD, SA, R) |
| `git add <file>` | Prepara 1 archivo para commit |
| `git add .` | Prepara TODOS los archivos |
| `git commit -m "mensaje"` | Guarda cambios (sin abrir VIM) |
| `git commit` | Abre VIM para mensajes más largos |

### 🌐 Sincronizar con GitHub
| Comando | Qué hace |
|---------|----------|
| `git push` | Sube tus commits a GitHub |
| `git pull` | Trae cambios de tus compañeros |
| `git fetch` | Solo descarga sin fusionar |

### 🌳 Ramas (Para trabajar en paralelo)
| Comando | Qué hace |
|---------|----------|
| `git branch` | Ver todas las ramas |
| `git branch "nombre"` | Crear una nueva rama |
| `git checkout "nombre"` | Cambiar a una rama |
| `git merge "nombre"` | Fusionar rama con main |

### 👀 Ver Cambios e Historial
| Comando | Qué hace |
|---------|----------|
| `git diff <file>` | Ver diferencias en un archivo |
| `git log --oneline` | Ver historial de commits |
| `git show <commit>` | Ver detalles de un commit |

### ↩️ Deshacer Cambios (¡Cuidado!)
| Comando | Qué hace |
|---------|----------|
| `git checkout -- <file>` | Revertir cambios de 1 archivo |
| `git restore <file>` | Descartar cambios (forma moderna) |
| `git reset HEAD <file>` | Sacar archivo del Staging Area |

---

## 🎮 VIM - Editor de Texto en Consola

Cuando usas `git commit` sin `-m`, se abre VIM automáticamente:

**Pasos:**
1. Presiona **`i`** → Modo INSERT (ahora puedes escribir)
2. Escribe tu mensaje
3. Presiona **`Esc`** → Salir del modo INSERT
4. Escribe **`:wq`** y presiona Enter → Guardar y salir

---

## 📁 .gitignore - Qué NO subir a GitHub

Archivo especial que dice a Git qué archivos ignorar (no subir).

**Ejemplos comunes:**
```
node_modules/          # Dependencias de Node.js
*.log                  # Archivos de log
.env                   # Variables de entorno (¡IMPORTANTE!)
__pycache__/          # Cache de Python
*.pyc                 # Compilados de Python
.DS_Store             # Archivos del sistema Mac
*.exe                 # Ejecutables
*.pdf                 # Documentos grandes
```

---

## 💡 CONCEPTOS IMPORTANTES

### Las 3 Áreas de Git

1. **Working Directory (WD)** → Tus archivos en la computadora
2. **Staging Area (SA)** → Archivos preparados (con `git add`)
3. **Repository (R)** → Historial guardado (con `git commit`)

**Flujo:** WD → (git add) → SA → (git commit) → R → (git push) → GitHub

### Master vs Main

- `master` = rama principal en repositorios antiguos
- `main` = rama principal en repositorios nuevos
- Son lo mismo, solo cambió el nombre

---

## 📌 EJEMPLOS PRÁCTICOS

### Ejemplo 1: Tu primer commit
```bash
git status
git add .
git commit -m "Primer commit - agregué archivo app.js"
git push
```

### Ejemplo 2: Ver qué cambiaste
```bash
git diff app.js          # Ver diferencias
git log --oneline        # Ver historial
git show abc1234         # Ver un commit específico
```

### Ejemplo 3: Trabajar en una rama nueva
```bash
git branch feature-login      # Crear rama
git checkout feature-login    # Cambiar a ella
# ... editas archivos ...
git add .
git commit -m "Agregué login"
git push
```

---

## ⚠️ ERRORES COMUNES

| Error | Solución |
|-------|----------|
| "fatal: not a git repository" | Haz `git init` o `git clone <URL>` |
| "nothing to commit" | No hay cambios, haz `git add .` primero |
| "VIM se abrió y no sé qué hacer" | Presiona `i`, escribe, `Esc`, `:wq` |
| "rejected ... (non-fast-forward)" | Haz `git pull` antes de `git push` |
