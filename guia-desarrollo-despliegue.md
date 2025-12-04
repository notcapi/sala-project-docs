# Guía del Proceso de Desarrollo y Despliegue Web

Esta guía explica de forma sencilla cómo se desarrolla y despliega tu página web, desde la creación de archivos hasta que está disponible en Internet con tu dominio personalizado.

---

## 📋 Índice

1. [Herramientas y Programas Utilizados](#herramientas-y-programas-utilizados)
2. [Fase 1: Desarrollo Local](#fase-1-desarrollo-local)
3. [Fase 2: Control de Versiones](#fase-2-control-de-versiones)
4. [Fase 3: Despliegue en Vercel](#fase-3-despliegue-en-vercel)
5. [Fase 4: Vinculación del Dominio](#fase-4-vinculación-del-dominio)
6. [Actualizaciones Futuras](#actualizaciones-futuras)

---

## 🛠️ Herramientas y Programas Utilizados

### Desarrollo
- **Visual Studio Code (VS Code)**: Editor de código donde se escriben y editan todos los archivos del proyecto
- **Node.js**: Entorno que permite ejecutar JavaScript en el ordenador (necesario para el desarrollo)
- **npm**: Gestor de paquetes que instala las librerías y dependencias necesarias

### Control de Versiones
- **Git**: Sistema que guarda un historial de todos los cambios realizados en el código
- **GitHub**: Plataforma en la nube donde se almacena el código del proyecto de forma segura

### Despliegue y Hosting
- **Vercel**: Plataforma que aloja tu página web y la hace accesible en Internet
- **Proveedor de Dominio**: Servicio donde compraste tu dominio (ej: GoDaddy, Namecheap, Google Domains)

### Navegador Web
- **Chrome/Firefox/Safari**: Para probar la página web durante el desarrollo

---

## 💻 Fase 1: Desarrollo Local

### ¿Qué sucede aquí?
En esta fase, el desarrollador crea y modifica los archivos de tu página web en su ordenador.

### Proceso paso a paso:

#### 1. **Configuración Inicial del Proyecto**
   - Se crea una carpeta para el proyecto (ej: `salatheproject`)
   - Se inicializa un proyecto con **Vite** (herramienta moderna para desarrollo web)
   - Comando utilizado: `npm create vite@latest`

#### 2. **Instalación de Dependencias**
   - Se instalan todas las librerías necesarias (React, TypeScript, etc.)
   - Comando: `npm install`
   - Esto crea una carpeta `node_modules` con miles de archivos de código reutilizable

#### 3. **Estructura de Archivos Creada**
   ```
   salatheproject/
   ├── components/          # Componentes reutilizables (Hero, BookingBar, etc.)
   ├── locales/            # Archivos de traducción (es.json, en.json)
   ├── api/                # Funciones del servidor (envío de emails)
   ├── utils/              # Funciones auxiliares (cálculos de precios)
   ├── index.html          # Página principal HTML
   ├── index.css           # Estilos visuales de la página
   ├── main.tsx            # Punto de entrada de la aplicación
   ├── package.json        # Lista de dependencias del proyecto
   └── vite.config.ts      # Configuración de Vite
   ```

#### 4. **Desarrollo de Componentes**
   - Se crean archivos `.tsx` (TypeScript + React) para cada sección:
     - `Hero.tsx`: Sección principal con título y descripción
     - `BookingBar.tsx`: Formulario de reservas
     - `Details.tsx`: Detalles del estudio
     - `Gallery.tsx`: Galería de fotos
   
#### 5. **Servidor de Desarrollo Local**
   - Se ejecuta: `npm run dev`
   - Esto inicia un servidor local en `http://localhost:5173`
   - El desarrollador puede ver los cambios en tiempo real en el navegador
   - Cada vez que se guarda un archivo, la página se actualiza automáticamente

#### 6. **Pruebas Locales**
   - Se prueba la funcionalidad: formularios, validaciones, cálculos
   - Se verifica el diseño en diferentes tamaños de pantalla
   - Se corrigen errores y se ajustan estilos

---

## 🔄 Fase 2: Control de Versiones

### ¿Qué sucede aquí?
Los cambios se guardan de forma organizada y se suben a GitHub para tener un respaldo en la nube.

### Proceso paso a paso:

#### 1. **Inicialización de Git**
   - En la carpeta del proyecto se ejecuta: `git init`
   - Esto crea un repositorio local que guardará el historial de cambios

#### 2. **Configuración de GitHub**
   - Se crea un repositorio en GitHub.com (ej: `notcapi/sala-the-project`)
   - Se vincula el repositorio local con GitHub:
     ```bash
     git remote add origin https://github.com/notcapi/sala-the-project.git
     ```

#### 3. **Guardado de Cambios (Commits)**
   - Cuando se completa una funcionalidad, se guardan los cambios:
     ```bash
     git add .                          # Prepara todos los archivos modificados
     git commit -m "Descripción cambio" # Guarda los cambios con un mensaje
     ```
   - Cada commit es como una "fotografía" del proyecto en ese momento

#### 4. **Subida a GitHub (Push)**
   - Los commits se suben a GitHub:
     ```bash
     git push origin main
     ```
   - Ahora el código está respaldado en la nube y accesible desde cualquier lugar

#### 5. **Ventajas del Control de Versiones**
   - Historial completo de cambios
   - Posibilidad de volver a versiones anteriores
   - Colaboración entre múltiples desarrolladores
   - Respaldo automático del código

---

## 🚀 Fase 3: Despliegue en Vercel

### ¿Qué sucede aquí?
Tu página web se publica en Internet y se hace accesible para cualquier persona.

### Proceso paso a paso:

#### 1. **Creación de Cuenta en Vercel**
   - Se accede a [vercel.com](https://vercel.com)
   - Se crea una cuenta (normalmente vinculada con GitHub)

#### 2. **Importación del Proyecto**
   - En Vercel, se selecciona "New Project"
   - Se elige el repositorio de GitHub: `notcapi/sala-the-project`
   - Vercel detecta automáticamente que es un proyecto Vite

#### 3. **Configuración del Proyecto**
   - **Framework Preset**: Vite
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - **Install Command**: `npm install`

#### 4. **Variables de Entorno**
   - Se configuran variables secretas necesarias (ej: claves de API):
     - `VITE_RESEND_API_KEY`: Para el servicio de envío de emails
     - Estas se añaden en la sección "Environment Variables" de Vercel

#### 5. **Proceso de Build (Construcción)**
   - Vercel ejecuta automáticamente:
     ```bash
     npm install        # Instala dependencias
     npm run build      # Compila el proyecto para producción
     ```
   - Esto genera archivos optimizados en la carpeta `dist/`
   - Los archivos se minimizan (reducen tamaño) para carga más rápida

#### 6. **Despliegue Automático**
   - Vercel sube los archivos compilados a sus servidores
   - Asigna una URL temporal: `https://sala-the-project.vercel.app`
   - La página ya está en línea y accesible desde cualquier dispositivo

#### 7. **Despliegues Continuos**
   - Cada vez que se hace `git push` a GitHub, Vercel:
     - Detecta el cambio automáticamente
     - Ejecuta el build
     - Despliega la nueva versión
   - **No se requiere intervención manual** para actualizar la página

---

## 🌐 Fase 4: Vinculación del Dominio

### ¿Qué sucede aquí?
Se conecta tu dominio personalizado (ej: `estudiosexclusivo.com`) con la página alojada en Vercel.

### Proceso paso a paso:

#### 1. **Adición del Dominio en Vercel**
   - En el proyecto de Vercel, ir a "Settings" → "Domains"
   - Añadir el dominio: `estudiosexclusivo.com`
   - También añadir: `www.estudiosexclusivo.com`

#### 2. **Obtención de Registros DNS**
   - Vercel proporciona registros DNS que deben configurarse:
     - **Registro A**: Apunta el dominio raíz a la IP de Vercel
     - **Registro CNAME**: Apunta `www` a Vercel
   
   Ejemplo:
   ```
   Tipo: A
   Nombre: @
   Valor: 76.76.21.21
   
   Tipo: CNAME
   Nombre: www
   Valor: cname.vercel-dns.com
   ```

#### 3. **Configuración en el Proveedor de Dominio**
   - Acceder al panel de control del proveedor (GoDaddy, Namecheap, etc.)
   - Ir a la sección "DNS Management" o "Gestión de DNS"
   - Añadir/modificar los registros DNS proporcionados por Vercel
   - Guardar los cambios

#### 4. **Propagación DNS**
   - Los cambios DNS tardan en propagarse: **entre 5 minutos y 48 horas**
   - Durante este tiempo, algunas personas pueden ver la página antigua o ninguna
   - Es un proceso automático que no se puede acelerar

#### 5. **Verificación en Vercel**
   - Vercel verifica automáticamente la configuración DNS
   - Cuando detecta que está correcta, muestra: "Valid Configuration"
   - El dominio ahora apunta a tu página web

#### 6. **Certificado SSL (HTTPS)**
   - Vercel genera automáticamente un certificado SSL gratuito
   - Esto hace que tu página sea segura (aparece el candado 🔒 en el navegador)
   - Se activa automáticamente, sin configuración adicional

#### 7. **Redirecciones Automáticas**
   - Vercel configura redirecciones:
     - `http://` → `https://` (fuerza conexión segura)
     - `www.dominio.com` → `dominio.com` (o viceversa, según preferencia)

---

## 🔄 Actualizaciones Futuras

### ¿Cómo se actualizan contenidos o funcionalidades?

#### Proceso Simplificado:
1. **Desarrollo Local**
   - El desarrollador modifica archivos en VS Code
   - Prueba los cambios en `localhost:5173`

2. **Guardar Cambios**
   ```bash
   git add .
   git commit -m "Actualización: descripción del cambio"
   git push origin main
   ```

3. **Despliegue Automático**
   - Vercel detecta el push a GitHub
   - Ejecuta el build automáticamente
   - Despliega la nueva versión en 1-3 minutos
   - La página se actualiza sin intervención manual

#### Tipos de Actualizaciones Comunes:

**Cambios de Contenido:**
- Modificar textos en archivos de traducción (`locales/es.json`)
- Actualizar imágenes de la galería
- Cambiar precios o descripciones

**Nuevas Funcionalidades:**
- Añadir nuevas secciones
- Integrar servicios externos (pagos, calendarios)
- Mejorar formularios o validaciones

**Correcciones:**
- Arreglar errores (bugs)
- Optimizar rendimiento
- Mejorar diseño responsive

---

## 📊 Resumen del Flujo Completo

```
┌─────────────────────────────────────────────────────────────┐
│                    DESARROLLO LOCAL                          │
│  VS Code + Node.js + npm                                     │
│  - Crear/editar archivos                                     │
│  - Ejecutar: npm run dev                                     │
│  - Probar en localhost:5173                                  │
└──────────────────┬──────────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────────┐
│                  CONTROL DE VERSIONES                        │
│  Git + GitHub                                                │
│  - git add .                                                 │
│  - git commit -m "mensaje"                                   │
│  - git push origin main                                      │
└──────────────────┬──────────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────────┐
│                  DESPLIEGUE AUTOMÁTICO                       │
│  Vercel                                                      │
│  - Detecta cambios en GitHub                                 │
│  - Ejecuta: npm install && npm run build                     │
│  - Despliega archivos optimizados                            │
└──────────────────┬──────────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────────┐
│                    PÁGINA EN LÍNEA                           │
│  https://tudominio.com                                       │
│  - Accesible desde cualquier dispositivo                     │
│  - Certificado SSL (segura)                                  │
│  - Actualizaciones automáticas                               │
└─────────────────────────────────────────────────────────────┘
```

---

## ❓ Preguntas Frecuentes

### ¿Cuánto tiempo tarda un cambio en verse reflejado?
- **Desarrollo local**: Instantáneo (al guardar el archivo)
- **Despliegue en Vercel**: 1-3 minutos después del push
- **Cambios DNS**: 5 minutos a 48 horas (solo al configurar el dominio inicialmente)

### ¿Qué pasa si hay un error en el código?
- Vercel detecta el error durante el build
- No despliega la versión con errores
- La versión anterior sigue funcionando
- Se notifica el error para que se corrija

### ¿Se puede revertir a una versión anterior?
- Sí, Vercel guarda todas las versiones anteriores
- Se puede hacer rollback con un clic en el panel de Vercel
- También se puede revertir usando Git

### ¿Cuánto cuesta mantener la página?
- **Vercel**: Plan gratuito para proyectos pequeños/medianos
- **GitHub**: Gratuito para repositorios públicos
- **Dominio**: Renovación anual (varía según proveedor)
- **Servicios adicionales**: Según uso (ej: emails con Resend)

### ¿Necesito conocimientos técnicos para actualizar contenidos?
- **Textos simples**: Se pueden editar directamente en GitHub (interfaz web)
- **Cambios complejos**: Requieren conocimientos de desarrollo
- **Recomendación**: Contactar al desarrollador para cambios importantes

---

## 📞 Soporte y Mantenimiento

Para cualquier actualización, corrección o nueva funcionalidad, el proceso es:

1. **Comunicar los cambios deseados** al desarrollador
2. El desarrollador implementa los cambios localmente
3. Prueba y valida la funcionalidad
4. Sube los cambios a GitHub
5. Vercel despliega automáticamente
6. Se verifica que todo funcione correctamente en producción

**Tiempo estimado**: Desde minutos (cambios simples) hasta días (funcionalidades complejas)

---

*Documento creado para explicar el proceso de desarrollo y despliegue de forma clara y accesible para clientes sin conocimientos técnicos.*
