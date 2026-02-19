# 📋 Eliminación de Archivos en Git - Ejemplo Práctico

## ¿Qué pasó en "lab doo"?

En la carpeta `lab doo` se eliminaron varios archivos. Este documento explica cómo hacerlo correctamente en Git.

---

## ✅ FORMA CORRECTA: Eliminar archivos y registrarlo en Git

### Opción 1: Eliminar con Git (Recomendado)

```bash
cd lab\ doo

# Eliminar UN archivo específico
git rm archivo_antiguo.txt

# Eliminar MÚLTIPLES archivos
git rm archivo1.txt archivo2.txt archivo3.txt

# Eliminar TODOS los archivos de un tipo
git rm *.docx

# Guardar la eliminación en un commit
git commit -m "Eliminar archivos obsoletos de lab doo"

# Subir a GitHub
git push
```

### Opción 2: Eliminar manualmente + Git

```bash
# Eliminas los archivos manualmente en Windows
# (Click derecho → Eliminar)

# Luego le dices a Git que note los cambios
git status

# Verás qué archivos fueron eliminados
# Prepáralos:
git add .

# Crea un commit
git commit -m "Eliminar archivos obsoletos"

# Sube a GitHub
git push
```

---

## 📝 Mensajes de Commit Claros para Eliminaciones

**MALO:**
```
git commit -m "delete files"
git commit -m "cambios"
git commit -m "actualización"
```

**BUENO:**
```
git commit -m "Eliminar archivos de prueba de la carpeta lab doo"
git commit -m "Remover documentos docx duplicados"
git commit -m "Limpiar archivos antiguos de laboratorio"
```

**EXCELENTE (con contexto):**
```
git commit -m "Eliminar archivos obsoletos de lab doo

- Removido: archivo_antiguo_v1.txt
- Removido: laboratorio_prueba.docx
- Razón: Archivos de prueba sin usar
- Mantener: laboratorio_1702824.docx (archivo activo)"
```

---

## 🔍 Ver qué archivos se eliminaron

```bash
# Ver cambios recientes
git log --oneline

# Ver detalles de un commit (qué se eliminó)
git show abc1234

# Ver diferencias (archivos eliminados en rojo con -)
git diff HEAD~1

# Ver historial completo de un archivo (aunque esté eliminado)
git log -- archivo_eliminado.txt
```

---

## ⚠️ ERRORES COMUNES

| Problema | Solución |
|----------|----------|
| "Eliminé archivos pero Git no los ve" | Haz `git add .` después de eliminar |
| "No recuerdo qué eliminé" | Haz `git status` para ver cambios pendientes |
| "Quiero RECUPERAR un archivo eliminado" | `git restore archivo.txt` |
| "Quiero deshacer la eliminación" | `git checkout -- archivo.txt` |

---

## 🔄 Recuperar un archivo eliminado (si te arrepientes)

```bash
# Si aún no hiciste commit:
git restore archivo.txt
git checkout -- archivo.txt

# Si ya hiciste commit:
git revert abc1234  # Crea un nuevo commit que revierta la eliminación
```

---

## 📊 Buen Workflow para Limpiar Archivos

1. **Identifica qué eliminar**
   - Archivos de prueba viejos
   - Duplicados
   - Archivos que ya no se usan

2. **Documéntalo** (en un .md o comentario)
   - Qué se elimina
   - Por qué se elimina
   - Qué se mantiene

3. **Haz commits separados**
   ```bash
   git commit -m "Eliminar archivos de prueba"
   git commit -m "Remover documentos duplicados"
   git commit -m "Limpiar laboratorios antiguos"
   ```

4. **Sube a GitHub**
   ```bash
   git push
   ```

5. **Notifica a tu equipo** (si trabajas en equipo)
   - Qué se eliminó
   - Por qué se eliminó

---

## 💡 Consejo: Antes de Eliminar Mucho

Si vas a eliminar muchos archivos, crea una rama primero:

```bash
git branch limpieza-archivos
git checkout limpieza-archivos

# Aquí elimina archivos
git add .
git commit -m "Eliminar archivos obsoletos"

# Revisa en GitHub cómo se ve
git push

# Si todo está bien, fusiona con main
git checkout main
git merge limpieza-archivos
git push

# Elimina la rama temporal
git branch -d limpieza-archivos
```

Esto evita que accidentalmente elimines algo importante.
