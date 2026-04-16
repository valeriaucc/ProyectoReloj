# Instrucciones para desplegar en Vercel

## Paso 1: Inicializar repositorio Git (si no lo tienes)

```bash
cd c:\Users\luzva\ProyectoReloj\Clock
git init
git add .
git commit -m "Initial commit - Clock SIGYE project"
```

## Paso 2: Crear repositorio en GitHub

1. Ve a https://github.com/new
2. Crea un nuevo repositorio con el nombre que desees (ej: ProyectoReloj)
3. NO inicialices con README (ya tienes archivos locales)
4. Copia la URL del repositorio

## Paso 3: Conectar repositorio local con GitHub

```bash
git remote add origin https://github.com/TU_USUARIO/TU_REPOSITORIO.git
git branch -M main
git push -u origin main
```

Reemplaza:
- `TU_USUARIO` con tu usuario de GitHub
- `TU_REPOSITORIO` con el nombre del repositorio

## Paso 4: Desplegar en Vercel

### Opción A: Usando la interfaz de Vercel (Recomendado)

1. Ve a https://vercel.com/
2. Inicia sesión o crea una cuenta
3. Haz clic en "New Project"
4. Selecciona "Import Git Repository"
5. Pega la URL de tu repositorio de GitHub
6. Vercel debería detectar automáticamente la configuración de `vercel.json`
7. Haz clic en "Deploy"

### Opción B: Usando Vercel CLI

```bash
npm install -g vercel
vercel login
vercel
```

## Resultado

Después del despliegue:
- Tu aplicación estará disponible en: `https://tu-proyecto.vercel.app`
- Obtén la URL exacta en el dashboard de Vercel

## Archivos creados para Vercel

- `vercel.json` - Configuración de Vercel
- `api/index.py` - Punto de entrada para Vercel
- `.gitignore` - Archivos a ignorar en Git

La estructura es la siguiente:
```
Clock/
├── api/
│   └── index.py (punto de entrada para Vercel)
├── backend/
│   ├── static/
│   ├── templates/
│   └── models/
├── vercel.json
├── .gitignore
├── App.py
└── requirements.txt
```

## Notas importantes

- El servidor estará disponible en Vercel automáticamente
- Los archivos estáticos (CSS, JS) se sirven desde `backend/static/`
- Las plantillas HTML se sirven desde `backend/templates/`
- Vercel ejecutará automáticamente las actualizaciones cuando hagas push a GitHub
