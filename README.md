# Playwright E2E Testing Project

Este proyecto es una suite de pruebas end-to-end (E2E) utilizando Playwright para probar tanto una aplicación de tienda de bagels como una tienda de herramientas.Es un proyecto siguiendo el curso de playwright-essential-training-abstractions-fixtures-and-complex-scenarios de LinkedIn Learning.

## 🚀 Características

- Pruebas E2E con Playwright
- Soporte para múltiples navegadores (Chromium, WebKit, dispositivos móviles)
- Tests para dos aplicaciones diferentes:
  - Bagel Shop (aplicación demo)
  - Practice Software Testing Toolshop
- Configuración TypeScript
- Patrón Page Object Model
- Data factories para creación de datos
- Reportes HTML y en consola
- Soporte para ejecución en CI

## 📋 Prerrequisitos

- Node.js >= 18.0.0
- npm

## 🛠️ Instalación

1. Clona el repositorio
2. Instala las dependencias:
```bash
npm install
```

3. Instala la aplicación Bagel Shop:
```bash
npm run install:bagel-shop
```

## 🏃‍♂️ Comandos de Ejecución

- **Iniciar la aplicación Bagel Shop**: `npm start`
- **Ejecutar todos los tests**: `npm test`
- **Ejecutar tests solo en Chromium**: `npm run test:chromium`
- **Ejecutar tests marcados con @first**: `npm run test:first`
- **Ejecutar tests contra servidor local**: `npm run test:local`
- **Ejecutar tests y mostrar reporte**: `npm run test:report`
- **Ejecutar tests en modo UI**: `npm run test:ui`

## 📁 Estructura del Proyecto

```
├── bagel-shop/                 # Aplicación demo de tienda de bagels
│   ├── index.html             # Página principal
│   ├── menu.html              # Página de menú
│   ├── order.html             # Página de pedidos
│   ├── contact.html           # Página de contacto
│   ├── style.css              # Estilos
│   ├── js/                    # Scripts JavaScript
│   └── package.json           # Dependencias de la app
├── lib/                       # Utilidades y helpers
│   ├── datafactory/           # Factories para creación de datos
│   ├── fixtures/              # Fixtures de Playwright
│   ├── helpers/               # Funciones auxiliares
│   └── pages/                 # Page Objects
├── tests/                     # Tests
│   ├── auth.setup.ts          # Setup de autenticación
│   ├── api/                   # Tests de API
│   ├── bagel-shop/            # Tests de la tienda de bagels
│   ├── checkout/              # Tests de checkout
│   ├── homepage/              # Tests de homepage
│   └── login/                 # Tests de login
├── .hars/                     # Archivos HAR para mocking
├── global.d.ts                # Definiciones TypeScript globales
├── playwright.config.ts       # Configuración de Playwright
└── package.json              # Dependencias y scripts
```

## 🧪 Tipos de Tests Incluidos

### Tests de Bagel Shop
- Smoke test de la página principal
- Tests de contacto con manejo de diálogos
- Tests de menú con interacción de tabla
- Tests de pedidos con subida de archivos
- Tests de popups y ventanas emergentes

### Tests de Toolshop
- Tests de homepage (con y sin autenticación)
- Tests de login y registro
- Tests de API
- Tests de checkout
- Tests de mensajes y contacto

## ⚙️ Configuración

### Variables de Entorno

Crea un archivo `.env` en la raíz del proyecto con:

```env
URL=http://localhost:5173
API_URL=https://api.practicesoftwaretesting.com
```

### Configuración de Playwright

El archivo `playwright.config.ts` incluye:

- Timeouts configurables
- Proyectos para diferentes navegadores
- Configuración de reportes
- Configuración de tracing y screenshots
- Custom matchers (ej: `toBeNumber()`)

## 🎯 Ejemplos de Uso

### Ejecutar tests específicos

```bash
# Tests de la tienda de bagels
npx playwright test tests/bagel-shop/

# Tests de API
npx playwright test tests/api/

# Tests con etiqueta específica
npx playwright test --grep "checkout"
```

### Ejecutar en modo headed

```bash
npx playwright test --headed
```

### Generar reportes

```bash
# Reporte HTML
npx playwright show-report

# Reporte en línea de comandos
npx playwright test --reporter=list
```

## 🔧 Custom Matchers

El proyecto incluye matchers personalizados:

```typescript
// Verificar que un valor es numérico
expect(price).toBeNumber();
```




