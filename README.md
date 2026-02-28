# Journal Trading - Despliegue en Cloudflare Pages

## 🚀 Configuración Paso a Paso en Cloudflare Pages (Desde Cero)

### Paso 1: Crear Cuenta en Cloudflare
1. Ve a [https://dash.cloudflare.com/sign-up](https://dash.cloudflare.com/sign-up)
2. Regístrate con tu email o usa Google/GitHub
3. Verifica tu email si es necesario
4. Elige el plan gratuito (Free)

### Paso 2: Subir Código a un Repositorio
1. Crea una cuenta en [GitHub](https://github.com) si no tienes una
2. Crea un nuevo repositorio llamado `journal-trading`
3. Sube todos los archivos del proyecto:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/tu-usuario/journal-trading.git
   git push -u origin main
   ```

### Paso 3: Conectar Repositorio a Cloudflare Pages
1. Inicia sesión en [Cloudflare Dashboard](https://dash.cloudflare.com)
2. En el menú izquierdo, haz clic en **"Pages"**
3. Haz clic en **"Create a project"**
4. Selecciona **"Connect to Git"**
5. Elige **GitHub** y autoriza Cloudflare
6. Busca y selecciona tu repositorio `journal-trading`
7. Haz clic en **"Begin setup"**

### Paso 4: Configurar Build Settings
1. **Framework preset**: Selecciona `None` del menú desplegable
2. **Build command**: Escribe exactamente:
   ```
   echo "No build required"
   ```
3. **Build output directory**: Deja en blanco o escribe `/`
4. **Root directory**: Deja en blanco
5. Haz clic en **"Save and Deploy"**

### Paso 5: Configurar Variables de Entorno
1. Después del primer despliegue, ve a tu proyecto en Pages
2. Haz clic en la pestaña **"Settings"**
3. En el menú izquierdo, selecciona **"Environment variables"**
4. Haz clic en **"Add variable"** y agrega:

   **Variable 1:**
   - Variable name: `SUPABASE_URL`
   - Value: `https://ajpsrhedvrlsidiorqkz.supabase.co`
   - Environment: `Production` y `Preview`
   - Haz clic en **"Save"**

   **Variable 2:**
   - Variable name: `SUPABASE_ANON_KEY`
   - Value: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImFqcHNyaGVkdnJsc2lkaW9ycWt6Iiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzE2MDQ0NjIsImV4cCI6MjA4NzE4MDQ2Mn0.u8Z5d9euNroryAym5XvemAEDu3wQPnlgXwmy7BKVH8I`
   - Environment: `Production` y `Preview`
   - Haz clic en **"Save"**

### Paso 6: Redesplegar con Variables
1. Vuelve a la pestaña **"Deployments"**
2. Haz clic en el último despliegue
3. Haz clic en **"Retry deployment"** para aplicar las variables

### Paso 7: Verificar Despliegue
1. Espera a que el despliegue termine (1-2 minutos)
2. Haz clic en **"Visit site"** para ver tu aplicación
3. Verifica que:
   - La página carga correctamente
   - Puedes iniciar sesión con Supabase
   - El sidebar funciona sin duplicados

## 📋 Resumen de Configuración Técnica

### Configuración del Proyecto en Cloudflare Pages

- **Framework preset**: `None`
- **Build command**: `echo "No build required"`
- **Build output directory**: `/`
- **Root directory**: `/`

### Variables de Entorne Configuradas

```
SUPABASE_URL=https://ajpsrhedvrlsidiorqkz.supabase.co
SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImFqcHNyaGVkdnJsc2lkaW9ycWt6Iiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzE2MDQ0NjIsImV4cCI6MjA4NzE4MDQ2Mn0.u8Z5d9euNroryAym5XvemAEDu3wQPnlgXwmy7BKVH8I
```

### Archivos de Configuración Creados

- `_redirects`: Maneja las rutas de la SPA correctamente
- `.env.example`: Plantilla para variables de entorno
- `README.md`: Esta guía completa

## ✅ Características Implementadas

- ✅ Botón duplicado del sidebar eliminado
- ✅ Configuración de rutas para SPA con `_redirects`
- ✅ Variables de entorno de Supabase configuradas
- ✅ Build optimizado para aplicación estática
- ✅ Guía paso a paso completa

## 🔧 Notas Técnicas

- La aplicación usa Supabase como backend
- Es una Single Page Application (SPA) vanilla JavaScript
- No requiere Node.js ni proceso de build
- Compatible con Cloudflare Pages Functions si se necesita backend adicional
- El dominio será: `tu-proyecto.pages.dev`
