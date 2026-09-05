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

Abre la carpeta del proyecto `C:\Users\52249\.gemini\antigravity\scratch\github-profile-advanced` y realiza estos reemplazos sencillos:

1. **En `README.md`**:
   - Reemplaza todas las apariciones de `TU_USUARIO` por tu verdadero nombre de usuario de GitHub (ej. `alexdev`).
   - Reemplaza `https://linkedin.com/in/TU_USUARIO`, `https://TU_PORTAFOLIO.com`, y `tuemail@ejemplo.com` por tus enlaces reales.
   - Ajusta los badges de tu Tech Stack si deseas agregar o quitar alguna tecnología.

2. **En `.github/workflows/blog-post-workflow.yml`**:
   - Reemplaza la URL del feed RSS en `feed_list` por la tuya (Dev.to, Medium, Hashnode, WordPress, etc.).

---

## 🔑 Paso 3: Configurar Permisos de GitHub Actions

Para que las automatizaciones (Snake, WakaTime, Blog Posts) puedan actualizar tu perfil automáticamente:

1. Ve a tu repositorio en GitHub -> **Settings** (Configuración).
2. En el menú lateral izquierdo, haz clic en **Actions** -> **General**.
3. En la sección **Workflow permissions**, selecciona **"Read and write permissions"**.
4. Haz clic en **Save** (Guardar).

---

## 🔐 Paso 4: (Opcional) Configurar Secrets/Llaves para WakaTime y Métricas

### A) WakaTime (Tiempo de programación):
1. Crea una cuenta gratuita en [wakatime.com](https://wakatime.com) e instala la extensión en tu editor de código (VS Code, JetBrains, etc.).
2. En WakaTime, ve a **Account Settings** -> **API Key** y copia tu clave.
3. En tu repositorio de GitHub, ve a **Settings** -> **Secrets and variables** -> **Actions**.
4. Haz clic en **New repository secret**.
5. Nombre: `WAKATIME_API_KEY` | Valor: Pega tu clave de API de WakaTime.

### B) GitHub Metrics Token (Métricas avanzadas):
1. Crea un Personal Access Token (PAT) en GitHub: [github.com/settings/tokens](https://github.com/settings/tokens) con permisos `public_repo` y `read:user`.
2. Agrégalo en tu repositorio en **Settings** -> **Secrets and variables** -> **Actions** con el nombre `METRICS_TOKEN`.

---

## 📤 Paso 5: Subir los Archivos a GitHub

Puedes subir los archivos mediante comandos Git en tu terminal:

```bash
cd C:\Users\52249\.gemini\antigravity\scratch\github-profile-advanced

git init
git add .
git commit -m "feat: mi perfil avanzado de github con automatizaciones"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/TU_USUARIO.git
git push -u origin main --force
```

*(También puedes arrastrar los archivos directamente desde el navegador en la pestaña "Add file" -> "Upload files" en GitHub).*

---

## ⚡ Paso 6: Ejecutar las Automatizaciones por primera vez

1. Ve a la pestaña **Actions** en tu repositorio de GitHub.
2. Verás la lista de Workflows (`Generate Snake Contribution Animation`, `Latest Blog Posts Workflow`, etc.).
3. Haz clic en cada uno y presiona el botón **Run workflow** -> **Run workflow**.

¡Y listo! 🎉 Tu perfil se actualizará automáticamente con banners animados, gráficos interactivos y estadísticas en tiempo real.
