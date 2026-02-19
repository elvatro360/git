# 📚 Índice de Guías Git - Elige por dónde empezar

## 🎯 ¿Por dónde empiezo?

**Si eres PRINCIPIANTE:** Lee esto primero
→ [`WORKFLOW_VISUAL.md`](WORKFLOW_VISUAL.md) - Diagramas y ejemplos prácticos

**Si quieres la REFERENCIA RÁPIDA:** 
→ [`GUIA_GIT_MEJORADA.md`](GUIA_GIT_MEJORADA.md) - Todos los comandos en tablas

**Si necesitas ELIMINAR ARCHIVOS:**
→ [`EJEMPLO_ELIMINACION_ARCHIVOS.md`](EJEMPLO_ELIMINACION_ARCHIVOS.md) - Cómo hacer limpieza correctamente

---

## 📋 Contenido de Cada Archivo

### 1️⃣ WORKFLOW_VISUAL.md
**Para:** Entender cómo funciona Git
- Flujo diario paso a paso
- Las 3 áreas de Git (lo más importante)
- Estados de archivos
- Top 10 comandos
- Ejemplo práctico: Tu primer día
- Comandos de rescate

### 2️⃣ GUIA_GIT_MEJORADA.md
**Para:** Referencia rápida
- Flujo básico
- Todos los comandos organizados en tablas
- Conceptos clave
- Ejemplos de uso
- Errores comunes

### 3️⃣ EJEMPLO_ELIMINACION_ARCHIVOS.md
**Para:** Limpiar y eliminar archivos correctamente
- Formas correctas de eliminar
- Mensajes de commit claros
- Cómo ver qué se eliminó
- Recuperar archivos si te arrepientes
- Workflow de limpieza

---

## ⚡ Guía Rápida por Tarea

### "¿Cómo hago mi primer commit?"
```bash
git add .
git commit -m "Descripción de cambios"
git push
```
📖 Ver: [`WORKFLOW_VISUAL.md`](WORKFLOW_VISUAL.md) - Sección "Ejemplo Práctico"

### "¿Cómo veo qué cambié?"
```bash
git status          # Ver cambios
git diff archivo    # Ver diferencias
git log --oneline   # Ver historial
```
📖 Ver: [`GUIA_GIT_MEJORADA.md`](GUIA_GIT_MEJORADA.md) - Sección "Ver Cambios"

### "¿Cómo elimino archivos correctamente?"
```bash
git rm archivo.txt
git commit -m "Eliminar archivo obsoleto"
git push
```
📖 Ver: [`EJEMPLO_ELIMINACION_ARCHIVOS.md`](EJEMPLO_ELIMINACION_ARCHIVOS.md)

### "¿Cómo trabajo en una rama?"
```bash
git branch mi-rama
git checkout mi-rama
# ... edita ...
git add .
git commit -m "Mensaje"
git push
```
📖 Ver: [`GUIA_GIT_MEJORADA.md`](GUIA_GIT_MEJORADA.md) - Sección "Ramas"

### "¿Cómo traigo cambios de otros?"
```bash
git pull
```
📖 Ver: [`GUIA_GIT_MEJORADA.md`](GUIA_GIT_MEJORADA.md) - Sección "Sincronizar con GitHub"

### "Se me olvidó qué hacer"
👉 **Usa `git status` siempre** - Te dice exactamente qué hacer después

---

## 🎓 Orden Recomendado de Lectura

| Nivel | Orden |
|-------|-------|
| **Principiante (1er día)** | 1. WORKFLOW_VISUAL.md<br>2. GUIA_GIT_MEJORADA.md |
| **Intermedio (después de 1 semana)** | 1. GUIA_GIT_MEJORADA.md<br>2. EJEMPLO_ELIMINACION_ARCHIVOS.md |
| **Avanzado (después de 1 mes)** | Todos los documentos + experimenta |

---

## 💡 Lo Más Importante (Memoriza esto)

**El flujo diario:**
```
git status → git add . → git commit -m "..." → git push
```

**Las 3 áreas:**
```
Working Directory → Staging Area → Repository → GitHub
```

**Cuando dudes:**
```
git status
```

---

## 🆘 Problemas Comunes

| Problema | Solución Rápida |
|----------|-----------------|
| No sé qué pasó | `git status` |
| Cambié algo y me arrepentí | `git checkout -- archivo.txt` |
| Eliminé un archivo | `git restore archivo.txt` |
| No puedo hacer push | `git pull` primero |
| Estoy perdido en una rama | `git branch` para ver dónde estoy |

---

## 📞 Si Nada Funciona

1. **Abre Git Bash o Terminal**
2. **Escribe: `git status`**
3. **Lee el mensaje** (usualmente te dice qué hacer)
4. **Si ves rojo** → Haz `git add .`
5. **Si ves verde** → Haz `git commit -m "tu mensaje"`
6. **Si ves "nothing to commit"** → Haz `git push`

---

## 🔗 Relación Entre Documentos

```
START HERE (INDEX.md)
    ↓
WORKFLOW_VISUAL.md (aprende el concepto)
    ↓
GUIA_GIT_MEJORADA.md (aprende los comandos)
    ↓
EJEMPLO_ELIMINACION_ARCHIVOS.md (caso específico)
    ↓
¡Practica!
```

---

## ✨ Versión Ultra-Rápida (30 segundos)

```bash
# Configura tu usuario (1 vez)
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"

# Descarga un proyecto
git clone <URL>

# Edita archivos...

# Cada vez que terminas:
git add .
git commit -m "Descripción"
git push

# Para traer cambios de otros:
git pull
```

---

📌 **IMPORTANTE:** Estas guías están en la carpeta `/git` de tu proyecto.
Úsalas como referencia mientras aprendes. ¡Con la práctica, Git se volverá segundo naturaleza! 🚀
