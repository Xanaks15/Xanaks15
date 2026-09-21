# 🚀 Guía de Configuración: Perfil Avanzado de GitHub

Esta guía te guiará paso a paso para desplegar tu nuevo perfil de GitHub personalizado con todas las automatizaciones de GitHub Actions funcionando perfectamente.

---

## 📋 Paso 1: Crear el Repositorio Especial en GitHub

1. Ingresa a tu cuenta de GitHub y crea un **nuevo repositorio**: [github.com/new](https://github.com/new)
2. En **Repository name**, escribe exactamente tu **nombre de usuario de GitHub** (ej. si tu usuario es `alexdev`, el repositorio debe llamarse `alexdev`).
3. GitHub mostrará un mensaje indicando que es un *repositorio especial (Special Repository)*.
4. Asegúrate de marcarlo como **Público (Public)**.
5. Marca la casilla **"Add a README file"** o déjalo vacío si vas a subir los archivos desde tu computadora.

---

## ✏️ Paso 2: Personalizar tu Usuario en los Archivos

Abre tu copia local del repositorio de perfil y revisa estos valores:

1. **En `README.md`**:
   - Reemplaza todas las apariciones de `TU_USUARIO` por tu verdadero nombre de usuario de GitHub (ej. `alexdev`).
   - Reemplaza `https://linkedin.com/in/TU_USUARIO`, `https://TU_PORTAFOLIO.com`, y `tuemail@ejemplo.com` por tus enlaces reales.
   - Ajusta los badges de tu Tech Stack si deseas agregar o quitar alguna tecnología.

2. **Fuente del blog**:
   - En **Settings → Secrets and variables → Actions → Variables**, crea `BLOG_FEED_URL` con tu URL RSS personal.
   - Comprueba que la URL responde y contiene tus publicaciones. No uses el feed genérico de una plataforma.
   - El workflow informa de la configuración pendiente si la variable no existe.

---

## 🔑 Paso 3: Configurar Permisos de GitHub Actions

Para que las automatizaciones (Snake y Blog Posts) puedan actualizar tu perfil automáticamente:

Los jobs que actualizan archivos declaran `permissions: contents: write` en sus
workflows. No necesitas ampliar el permiso predeterminado de todos los workflows
del repositorio. Si una política de la organización impide esa escritura, revisa
esa política con su administrador.

---

## 📤 Paso 4: Subir los Archivos a GitHub

Puedes subir los archivos mediante comandos Git en tu terminal:

```bash
git clone https://github.com/Xanaks15/Xanaks15.git
cd Xanaks15
# Edita los archivos antes de preparar el commit.
git add .
git commit -m "chore: actualizar perfil"
git push origin main
```

*(También puedes arrastrar los archivos directamente desde el navegador en la pestaña "Add file" -> "Upload files" en GitHub).*

---

## ⚡ Paso 5: Ejecutar las Automatizaciones por primera vez

1. Ve a la pestaña **Actions** en tu repositorio de GitHub.
2. Verás la lista de Workflows (`Generate Snake Contribution Animation`, `Latest Blog Posts Workflow`, etc.).
3. Haz clic en cada uno y presiona el botón **Run workflow** -> **Run workflow**.

Comprueba que la ejecución termine correctamente. Blog necesita la URL RSS
indicada arriba; su comprobación no se omite si falta.
WakaTime y Metrics fueron retirados y no requieren secretos.
Las ejecuciones fallidas anteriores siguen apareciendo en el historial de Actions.
