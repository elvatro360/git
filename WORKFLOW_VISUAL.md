# 🎯 Workflow Visual de Git - Resumen Ejecutivo

## El Flujo Diario (Repite esto cada día)

```
┌─────────────────────────────────────────────────────────┐
│ 1. EDITAS TUS ARCHIVOS                                  │
│    (app.js, index.html, style.css, etc.)                │
└─────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────┐
│ 2. git status                                            │
│    (Ver qué cambió: archivos rojos = nuevos/modificados)│
└─────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────┐
│ 3. git add .                                            │
│    (Prepara todos los cambios para guardar)             │
└─────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────┐
│ 4. git commit -m "Descripción clara del cambio"         │
│    (Guarda los cambios con un mensaje)                  │
└─────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────┐
│ 5. git push                                             │
│    (Sube a GitHub para que otros vean)                  │
└─────────────────────────────────────────────────────────┘
```

---

## Las 3 Áreas (Lo MÁS importante de Git)

```
┌──────────────────────────────────────────────────────────────────┐
│                    WORKING DIRECTORY                              │
│              (Tu PC - Los archivos que ves)                      │
│  archivos.txt (rojo = cambios sin guardar)                       │
└──────────────────────────────────────────────────────────────────┘
                     ↓ (git add .)
┌──────────────────────────────────────────────────────────────────┐
│                    STAGING AREA                                   │
│         (Zona de espera - Preparados para commit)                │
│  archivos.txt (verde = listos para guardar)                      │
└──────────────────────────────────────────────────────────────────┘
                  ↓ (git commit -m "...")
┌──────────────────────────────────────────────────────────────────┐
│                    REPOSITORY (tu PC)                             │
│       (Historial guardado localmente - tu máquina)               │
│  ✓ archivos.txt (guardado en el historial)                       │
└──────────────────────────────────────────────────────────────────┘
                     ↓ (git push)
┌──────────────────────────────────────────────────────────────────┐
│                    GITHUB (en internet)                           │
│      (Remoto - para que otros accedan y colaboren)               │
│  ✓ archivos.txt (en la nube, compartido)                         │
└──────────────────────────────────────────────────────────────────┘
```

---

## Estados de un Archivo en Git

```
NUEVO ARCHIVO O MODIFICADO
         ↓
    ¿Cambios hechos? → SÍ
         ↓
    Untracked o Modified (ROJO en git status)
         ↓
    git add archivo.txt
         ↓
    Staged (VERDE en git status)
         ↓
    git commit -m "mensaje"
         ↓
    Committed (GUARDADO en el historial)
         ↓
    git push
         ↓
    En GitHub (COMPARTIDO)
```

---

## Diferencia: git add . vs git add <file>

```
git add .                    →  Prepara TODOS los cambios
                               (La que usas el 99% del tiempo)

git add archivo.txt          →  Prepara SOLO ese archivo
                               (Cuando quieres ser selectivo)

git add *.js                 →  Prepara todos los .js
                               (Patrón específico)
```

---

## Rama vs Ramas (Branches)

```
                    MAIN (rama principal)
                    ↓
         Commit 1 ← Commit 2 ← Commit 3
                          ↓
                    ¿Quieres hacer cambios grandes?
                    Crea una rama paralela:
                          ↓
              FEATURE-LOGIN (rama nueva)
                    ↓
         Cambio 1 ← Cambio 2 ← Cambio 3
                          ↓
                    ¿Está perfecto?
                    Fusiona con main:
                          ↓
         Commit 1 ← Commit 2 ← Commit 3 ← Cambio 1 ← Cambio 2 ← Cambio 3
```

---

## Comandos Más Usados (TOP 10)

| # | Comando | Cuándo usarlo | Frecuencia |
|---|---------|---------------|-----------|
| 1 | `git status` | Siempre, para ver qué cambió | 🔴 Cada 5 min |
| 2 | `git add .` | Después de editar | 🔴 Cada hora |
| 3 | `git commit -m "..."` | Cuando terminas algo | 🔴 Cada hora |
| 4 | `git push` | Cuando subes a GitHub | 🔴 Cada hora |
| 5 | `git pull` | Cuando bajascambios de otros | 🟡 Cada día |
| 6 | `git log --oneline` | Ver historial | 🟡 Cada día |
| 7 | `git branch` | Ver ramas | 🟢 1-2 veces/semana |
| 8 | `git checkout` | Cambiar de rama | 🟢 1-2 veces/semana |
| 9 | `git diff` | Ver qué cambiaste | 🟡 Cada día |
| 10 | `git clone` | Descargar un repo | 🟢 1-2 veces/semana |

---

## Ejemplo Práctico: Tu Primer Día

```bash
# ✅ Día 1 - Mañana
git clone https://github.com/usuario/proyecto.git
cd proyecto
# ... editas archivos ...
git status

# ✅ Día 1 - Tarde (cuando terminas)
git add .
git commit -m "Agregué la página de inicio"
git push

# ✅ Día 2 - Mañana
git pull  # Traer cambios de tus compañeros
# ... editas más ...
git add .
git commit -m "Agregué formulario de contacto"
git push

# ✅ Fin de semana - Quieres trabajar en algo grande sin romper main
git branch nueva-feature
git checkout nueva-feature
# ... editas mucho ...
git add .
git commit -m "Implementé login"
git push

# ✅ Lunes - Fusionas tu trabajo con main
git checkout main
git pull
git merge nueva-feature
git push
git branch -d nueva-feature
```

---

## 🚨 Cuando Algo Sale Mal

| Situación | Comando de rescate |
|-----------|-------------------|
| "Cambié un archivo y quiero revertir" | `git checkout -- archivo.txt` |
| "Agregué algo a staging y me arrepentí" | `git reset HEAD archivo.txt` |
| "Hice un commit malo" | `git revert abc1234` |
| "Borré un archivo y quiero recuperarlo" | `git restore archivo.txt` |
| "Git me pide hacer pull antes de push" | `git pull` luego `git push` |

---

## 📌 Mensajes de Commit: Cómo Hacerlos Bien

**❌ MALO:**
```
git commit -m "fix"
git commit -m "cambios"
git commit -m "actualización"
```

**✅ BUENO:**
```
git commit -m "Agregar validación en formulario de login"
git commit -m "Corregir error de espacios en CSS"
git commit -m "Actualizar base de datos con nuevas columnas"
```

**✨ EXCELENTE:**
```
git commit -m "Implementar autenticación con JWT

- Agregué endpoint POST /login
- Hash de contraseñas con bcrypt
- Token expira en 24 horas
- Validación de emails"
```

---

## 🎓 Resumen en 10 Puntos

1. Git guarda **historial** de cambios
2. Tienes 3 áreas: Working Dir → Staging Area → Repository
3. **git status** = tu mejor amigo (úsalo siempre)
4. **git add .** prepara cambios
5. **git commit -m "..."** guarda con descripción
6. **git push** sube a GitHub
7. **git pull** trae cambios de otros
8. Las **ramas** te permiten trabajar en paralelo
9. Mensajes claros = equipo feliz
10. Cuando dudes, haz **git status** 😄
