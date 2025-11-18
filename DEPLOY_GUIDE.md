# 🚀 Guía de Deploy: Legado Digital en GitHub y Vercel

## Paso 1: Preparar Git Localmente

### 1.1 Inicializar repositorio Git (si no lo está)
```bash
cd c:\Users\1\Blog-CyberSecurity
git init
```

### 1.2 Configurar usuario de Git (si es la primera vez)
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@example.com"
```

### 1.3 Crear archivo .gitignore (si no existe)
El proyecto debe tener un `.gitignore` con contenido similar a:
```
node_modules/
.env
.env.local
dist/
.astro/
.DS_Store
*.log
```

### 1.4 Hacer commit inicial
```bash
git add .
git commit -m "Proyecto Legado Digital - Refactorización completa para Notaría 27"
```

---

## Paso 2: Crear Repositorio en GitHub

### 2.1 Crear cuenta en GitHub (si no la tienes)
- Ir a https://github.com/join
- Registrarse con email y contraseña
- Verificar email

### 2.2 Crear nuevo repositorio
1. En GitHub, hacer clic en "New" (arriba a la derecha)
2. Llenar los datos:
   - **Repository name**: `legado-digital` o `notaria27-portal`
   - **Description**: "Portal digital para sucesiones en Notaría 27"
   - **Visibility**: Public (para que Vercel pueda acceder)
   - **Add .gitignore**: Node
   - **Add License**: MIT

3. Hacer clic en "Create repository"

### 2.3 Conectar repositorio local con GitHub
Después de crear el repo en GitHub, verás comandos. Ejecutar en terminal:

```bash
git remote add origin https://github.com/TU_USUARIO/legado-digital.git
git branch -M main
git push -u origin main
```

Reemplaza `TU_USUARIO` con tu usuario de GitHub.

---

## Paso 3: Configurar Variables de Entorno (Opcional)

Si tu proyecto necesita variables de entorno:

### 3.1 Crear archivo `.env.example`
```
# Ejemplo de variables (sin valores sensibles)
VITE_API_URL=https://api.ejemplo.com
```

### 3.2 Crear archivo `.env` en local (gitignore)
```
VITE_API_URL=tu_url_real
```

---

## Paso 4: Deploy en Vercel

### 4.1 Crear cuenta en Vercel
1. Ir a https://vercel.com/signup
2. Hacer clic en "Continue with GitHub"
3. Autorizar la aplicación
4. Llenar perfil

### 4.2 Importar proyecto desde GitHub
1. En Vercel dashboard, hacer clic en "New Project"
2. Hacer clic en "Import Git Repository"
3. Seleccionar el repositorio `legado-digital`
4. Vercel detectará que es un proyecto Astro automáticamente

### 4.3 Configurar build settings (opcional)
- **Framework Preset**: Astro
- **Build Command**: `pnpm run build`
- **Output Directory**: `dist`
- **Install Command**: `pnpm install`

### 4.4 Configurar variables de entorno (si aplica)
1. Ir a "Settings" → "Environment Variables"
2. Agregar variables si es necesario
3. Hacer clic en "Save"

### 4.5 Deploy
1. Hacer clic en "Deploy"
2. Esperar a que se complete
3. Tu sitio estará en `https://legado-digital-xxxx.vercel.app`

---

## Paso 5: Configurar Dominio Personalizado (Opcional)

Si tienes un dominio propio (ej: www.legado-digital.com):

### En Vercel:
1. Project Settings → Domains
2. Agregar dominio personalizado
3. Seguir instrucciones para configurar DNS

### En tu proveedor de dominio:
- Apuntar registros DNS a los servidores de Vercel
- Típicamente necesitas configurar CNAME o A records

---

## Paso 6: Configuración Automática de Deploy

### 6.1 Habilitar Preview Deployments
En Vercel → Settings → Git:
- ✅ **Deploy on every push**: Automático cada vez que haces push
- ✅ **Preview Deployments**: Para pull requests

### 6.2 Configurar Production Branch
- **Production Branch**: `main`

---

## Paso 7: Verificar Deploy

1. Ir a la URL de Vercel proporcionada
2. Verific que todos los módulos funcionan:
   - ✓ Página principal
   - ✓ Agendar citas
   - ✓ Checklist de documentos
   - ✓ Mi Sucesión
   - ✓ Calculadora
   - ✓ Dark mode

3. Probar en mobile (responsive)

---

## Paso 8: Futuros Cambios

### Para actualizar el proyecto:
```bash
# Hacer cambios locales
git add .
git commit -m "Descripción de cambios"
git push origin main
```

Vercel automáticamente desplegará los cambios.

---

## Troubleshooting

### Build falla en Vercel pero funciona localmente:
1. Verificar que `package.json` tiene las dependencias correctas
2. Ejecutar `pnpm install` localmente y commit `pnpm-lock.yaml`
3. Revisar logs en Vercel para ver error específico

### Dominio no funciona:
1. Esperar 24-48 horas para propagación DNS
2. Verificar configuración DNS en proveedor
3. Usar herramienta online para verificar registros DNS

### Variables de entorno no se cargan:
1. Verificar nombres exactos en Vercel
2. Usar `import.meta.env.VITE_*` en Astro
3. Redeploy después de agregar variables

---

## Información Útil

- **GitHub Education**: Si eres estudiante, obtén acceso gratuito a GitHub Pro
- **Vercel Free**: Incluye deploys ilimitados, perfecto para proyectos de aprendizaje
- **Custom Domain en Vercel**: Gratis el primer año si lo compras a través de Vercel

---

**Proyecto**: Legado Digital - Notaría 27  
**Fecha**: Noviembre 2025  
**Equipo**: Daniela Ospina, Sofía Manco, Belinda Carrillo, Kady Martinez
