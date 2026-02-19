# 🌐 Git: Aprende Control de Versiones

> Tutorial completo sobre cómo usar Git y GitHub

---

## 📑 Índice Rápido

- [¿Qué es Git?](#qué-es-git)
- [Conceptos Básicos](#conceptos-básicos)
- [Cómo Empezar](#cómo-empezar)
- [Temas Avanzados](#temas-avanzados)
- [Ejercicios Prácticos](#ejercicios-prácticos)
- [Recursos](#recursos)

---

## ❓ ¿Qué es Git?

### La Idea Simple

```
Git es como un "guardador de cambios" para tu código.

Imagina que escribes un documento importante:
❌ Sin Git:   Pierdes cambios accidentalmente
✅ Con Git:   Guardas cada versión y puedes volver atrás
```

### ¿Para Qué Sirve?

```
✅ Guardar versiones de tu código
✅ Trabajar con otras personas
✅ Deshacer errores fácilmente
✅ Ver quién cambió qué y cuándo
✅ Trabajar en múltiples características simultáneamente
```

---

## 📚 Conceptos Básicos

### Repositorio 📂
```
Un "repositorio" es una carpeta especial que guarda:
├─ Tu código actual
├─ Historial de todos los cambios
├─ Información de contribuyentes
└─ Configuración del proyecto

Carpeta normal:  📁 mi-proyecto/
Repositorio Git: 📁 mi-proyecto/.git/ (carpeta oculta)
```

### Commit 📸
```
Un "commit" es una foto del estado de tu código en ese momento.

Ej: "Agregué botón de login" = commit
    "Corregí bug de validación" = otro commit
    "Cambié colores del tema" = otro commit más

Cada commit tiene:
✓ Código guardado
✓ Descripción de cambios
✓ Fecha y hora
✓ Quién lo hizo
```

### Rama 🌳
```
Las ramas permiten trabajar en cosas diferentes simultáneamente:

main (rama principal - código funcionando)
  ├─ feature/login (nueva característica)
  ├─ bugfix/error-404 (arreglando bug)
  └─ experiment/nueva-idea (pruebas)

Al terminar, mezclas la rama de vuelta a main
```

### Push & Pull 🔄
```
Push = enviar tus cambios (arriba → servidor)
  git push origin main

Pull = traer cambios de otros (servidor → abajo)
  git pull origin main
```

---

## 🚀 Cómo Empezar

### Paso 1: Instalar Git
```bash
Windows:  Descarga de git-scm.com/download/win
Mac:      brew install git
Linux:    sudo apt install git
```

### Paso 2: Configurar Tu Nombre
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

### Paso 3: Crear Tu Primer Repositorio
```bash
mkdir mi-proyecto
cd mi-proyecto
git init
```

### Paso 4: Hacer Tu Primer Commit
```bash
# 1. Crear un archivo
echo "print('Hola Git!')" > app.py

# 2. Decir a Git que lo siga
git add app.py

# 3. Guardar con descripción
git commit -m "Mi primer commit: agregué app.py"

# Listo! Ya hiciste tu primer commit 🎉
```

---

## 💡 Temas Avanzados

### Ramificación (Branching)
```bash
# Ver ramas
git branch

# Crear rama nueva
git branch feature/login

# Cambiar a rama
git checkout feature/login

# Combinar: "Merge"
git checkout main
git merge feature/login
```

### Deshacer Cambios
```bash
# Si no commitiste aún
git restore archivo.py

# Si ya commitiste, vuelve atrás
git revert abc1234

# O resetea a un commit anterior
git reset --hard abc1234
```

### Historial
```bash
# Ver todos los commits
git log

# Ver cambios específicos
git show abc1234

# Ver quién cambió cada línea
git blame app.py
```

---

## 🎯 Ejercicios Prácticos

### Ejercicio 1: Mi Primer Repositorio (15 minutos)
```
1. Crea carpeta "mi-proyecto"
2. Inicia git: git init
3. Crea archivo "README.md"
4. Agrega a Git: git add .
5. Haz commit: git commit -m "Proyecto inicial"
6. Verifica: git log
```

### Ejercicio 2: Trabajar con Ramas (20 minutos)
```
1. Crea rama "feature/menu": git branch feature/menu
2. Cambia a esa rama: git checkout feature/menu
3. Crea archivo "menu.py"
4. Commit: git commit -m "Agregué menu"
5. Vuelve a main: git checkout main
6. Mezcla: git merge feature/menu
```

### Ejercicio 3: Colaboración en GitHub (30 minutos)
```
1. Crea cuenta en github.com
2. Crea nuevo repositorio "hola-mundo"
3. Clona: git clone <URL>
4. Haz cambios
5. Push: git push origin main
6. ¡Verifica en GitHub!
```

---

## 📊 Flujo de Trabajo Típico

### Día a Día
```
Mañana:
  git pull origin main           # Traigo últimos cambios
  git checkout -b feature/nueva  # Creo rama para trabajar
  
Durante el día:
  [haces cambios...]
  git add .
  git commit -m "Descripción"
  
Final del día:
  git push origin feature/nueva  # Subo mis cambios
  
Cuando terminas la tarea:
  git checkout main
  git merge feature/nueva        # Mezclo a principal
  git push origin main
```

---

## 🔒 Mejores Prácticas

### ✅ Haz esto
```
✓ Commits pequeños y frecuentes
✓ Mensajes descriptivos ("Arreglé bug X")
✓ Pull antes de Push
✓ Crea ramas para características
✓ Revisa código antes de mezclar
```

### ❌ Evita esto
```
✗ Commits enormes de todo
✗ Mensajes genéricos ("cambios")
✗ Pushear código roto
✗ Trabajar directo en main
✗ Mezclar sin revisar
```

---

## 📚 Recursos para Aprender

### Documentación
- 📖 [Pro Git Book](https://git-scm.com/book/es/v2) - Guía completa
- 📖 [Git Documentation](https://git-scm.com/doc) - Manual oficial
- 📖 [GitHub Guides](https://guides.github.com/) - Tutoriales GitHub

### Videos
- 🎥 "Git in 100 Seconds"
- 🎥 "Git and GitHub for Beginners"
- 🎥 "Advanced Git"

### Prácticas Interactivas
- 🎮 [Visualizing Git](https://git-school.github.io/visualizing-git/)
- 🎮 [Learn Git Branching](https://learngitbranching.js.org/)
- 🎮 [GitHub Learning Lab](https://lab.github.com/)

---

## 🎓 Checklist de Aprendizaje

- [ ] Entiendo qué es Git
- [ ] Instalé Git en mi computadora
- [ ] Hice mi primer commit
- [ ] Creé y usé ramas
- [ ] Subí cambios a GitHub
- [ ] Hice pull de cambios
- [ ] Manejé un conflicto de merge
- [ ] Revierto cambios correctamente

**Si marcaste todo ✓ → ¡Ya sabes Git! 🎉**

---

## 📞 Preguntas Comunes

### ¿Git es lo mismo que GitHub?
```
NO. 
Git = software para versionado (local)
GitHub = sitio web para compartir código (en línea)

Git solo en tu computadora ✓
GitHub es Git en la nube ✓
```

### ¿Necesito GitHub para usar Git?
```
NO. Git funciona sin GitHub.
Pero GitHub es muy útil para:
✓ Colaborar
✓ Hacer backup
✓ Compartir código
```

### ¿Qué es un "merge conflict"?
```
Sucede cuando:
1. Tú cambias línea 5
2. Otra persona cambia línea 5
3. Git no sabe cuál cambio usar

Solución: Revisa ambos cambios y elige cuál usar
```

### ¿Cómo deshacer un commit ya pusheado?
```
Opción 1 (segura): git revert abc1234
Opción 2 (peligrosa): git reset --hard abc1234
           (solo si nadie más usa ese código)
```

---

## 🏁 Siguientes Pasos

Después de dominar Git, aprende:

```
1. GitHub Pages  → Hospeda tu sitio web
2. CI/CD         → Automatiza tests
3. Colaboración  → Trabaja en equipo
4. Contribuye    → A proyectos open-source
```

---

<div align="center">

## ✅ ¡Felicidades!

### Ahora entiendes Git

**Siguiente proyecto:**

[🌐 PythonWeb](../pythonweb/README.md) - Aprende a hacer sitios web

---

*Tutorial completo | Sin códigos complicados | Fácil de seguir*

</div>
