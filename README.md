# Mini Ramo Flores - Sistema Integral de Gestión

**Aplicación web completa para gestión integral de emprendimiento de velas artesanales**

## 🎯 Descripción

Sistema empresarial moderno y funcional diseñado específicamente para la gestión del emprendimiento "Mini Ramo Flores". Centraliza información operativa, financiera y comercial del negocio de velas artesanales hechas a mano.

## 📦 Características Principales

### Módulos Implementados
- ✅ **Inventario** - Gestión de materias primas con alertas automáticas
- ✅ **Productos Terminados** - Catálogo con precios y stock
- ✅ **Recetas/Fórmulas** - Cálculo automático de costos de producción
- ✅ **Costos de Producción** - Análisis detallado con márgenes configurables
- ✅ **CRM de Clientes** - Base de datos completa con historial
- ✅ **Cotizaciones** - Profesionales y convertibles a pedidos
- ✅ **Pedidos** - Registro y seguimiento automatizado
- ✅ **Ventas** - Registro con descuento automático de inventario
- ✅ **Ingresos** - Registro y proyecciones financieras
- ✅ **Egresos/Gastos** - Clasificación por categoría
- ✅ **Dashboard Financiero** - Indicadores clave en tiempo real
- ✅ **Reportes y Estadísticas** - Exportables a Excel/PDF

### Funcionalidades Transversales
- 🎨 **Diseño Responsive** - Adaptable a móvil, tablet y desktop
- 🌙 **Panel Lateral Colapsable** - Más espacio para el contenido
- 💾 **Persistencia de Datos** - Sincronización en tiempo real con Firebase
- 🔐 **Autenticación Segura** - JWT y Firebase Auth
- 📊 **Exportación** - CSV, Excel, PDF
- 🔄 **Importación** - Datos desde Excel
-  **Indicadores de Salud Financiera** - Proyecciones y simulaciones

## 🛠️ Tech Stack

### Frontend
- **React 18** con TypeScript
- **Material-UI (MUI)** para componentes
- **React Router** para navegación
- **Axios** para HTTP requests

### Backend
- **Node.js** con Express.js
- **Firebase Admin SDK** para autenticación y base de datos
- **JWT** para autenticación
- **Joi** para validación

### Base de Datos & Almacenamiento
- **Firebase Firestore** - Base de datos en tiempo real
- **Firebase Authentication** - Autenticación de usuarios
- **Firebase Storage** - Almacenamiento de imágenes y documentos

## 🚀 Instalación Rápida

### Requisitos Previos
- **Node.js 16+** - [Descargar aquí](https://nodejs.org/)
- **npm** (viene incluido con Node.js)
- **Cuenta de Firebase** - [Crear cuenta gratuita](https://firebase.google.com/)

### Instalación Automática

**Windows:**
```bash
install.bat
```

**macOS/Linux:**
```bash
bash install.sh
```

### Configuración de Firebase

1. **Crear proyecto en Firebase:**
   - Ve a https://console.firebase.google.com/
   - Clic en "Agregar proyecto"
   - Nombre del proyecto: `mini-ramo-flores` (o el nombre que prefieras)
   - Clic en "Crear proyecto"

2. **Habilitar servicios:**
   - **Firestore Database:** Ve a Firestore → Crear base de datos → Modo de prueba → Habilitar
   - **Authentication:** Ve a Authentication → Comenzar → Correo electrónico/contraseña → Habilitar

3. **Obtener credenciales:**
   - Ve a Configuración del proyecto (icono de engranaje)
   - Ve a la pestaña "Cuentas de servicio"
   - Clic en "Generar nueva clave privada"
   - Descarga el archivo JSON
   - Renómbralo a `serviceAccountKey.json`
   - Colócalo en: `backend/src/config/`

4. **Configurar variables de entorno:**
```bash
# Backend
cp backend/.env.example backend/.env

# Frontend
cp frontend/.env.example frontend/.env.local
```

Edita `backend/.env` con tus credenciales de Firebase:
```env
PORT=5000
NODE_ENV=development
JWT_SECRET=tu_clave_secreta_minimo_32_caracteres
FIREBASE_API_KEY=tu_api_key
FIREBASE_AUTH_DOMAIN=tu_proyecto.firebaseapp.com
FIREBASE_PROJECT_ID=tu_project_id
FIREBASE_STORAGE_BUCKET=tu_proyecto.appspot.com
FIREBASE_MESSAGING_SENDER_ID=tu_sender_id
FIREBASE_APP_ID=tu_app_id
CORS_ORIGIN=http://localhost:3000
```

Edita `frontend/.env.local`:
```env
REACT_APP_API_URL=http://localhost:5000
```

### Ejecutar la Aplicación

**Opción 1: Ambos servidores juntos (recomendado)**
```bash
npm run dev
```

**Opción 2: Servidores separados**

Terminal 1 - Backend:
```bash
cd backend
npm run dev
```

Terminal 2 - Frontend:
```bash
cd frontend
npm start
```

### Acceder a la Aplicación
- **Frontend:** http://localhost:3000
- **Backend:** http://localhost:5000

### Credenciales Demo
- **Email:** demo@minifarolflores.com
- **Contraseña:** Demo123456

## 📖 Guía Detallada

Para instrucciones detalladas de instalación y configuración, consulta el archivo [SETUP.md](SETUP.md).

## 🔧 Solución de Problemas

### Error: "Firebase initialization failed"
- Verifica que `serviceAccountKey.json` esté en `backend/src/config/`
- Asegúrate de haber habilitado Firestore en Firebase Console
- Espera unos minutos para que los cambios se propaguen

### Error: "Port already in use"
- Cambia el puerto en `backend/.env`: `PORT=5001`

### Error: "CORS error"
- Verifica que `CORS_ORIGIN` en `backend/.env` sea `http://localhost:3000`
- Reinicia el servidor backend

Para más soluciones, consulta [SETUP.md](SETUP.md).

## 📁 Estructura del Proyecto

```
mini-ramo-flores-app/
├── backend/
│   ├── src/
│   │   ├── models/          # Esquemas de datos
│   │   ├── routes/          # Rutas API
│   │   ├── controllers/     # Lógica de negocio
│   │   ├── middleware/      # Autenticación, validación
│   │   ├── services/        # Servicios de negocio
│   │   └── utils/           # Utilidades
│   ├── .env.example
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/      # Componentes reutilizables
│   │   ├── pages/           # Páginas principales
│   │   ├── modules/         # Módulos funcionales
│   │   ├── store/           # Redux store
│   │   ├── services/        # API calls
│   │   ├── hooks/           # Custom hooks
│   │   ├── utils/           # Utilidades
│   │   ├── styles/          # Estilos globales
│   │   └── App.tsx
│   ├── .env.example
│   └── package.json
├── README.md
└── .gitignore
```

## 📋 Guía de Módulos

### 1. Inventario de Materia Prima
Registro y control de todos los materiales (cera, fragancias, pabilos, moldes, etc.) con alertas automáticas de stock bajo.

### 2. Productos Terminados
Catálogo de velas personalizadas con precios individuales, por pack y control de stock.

### 3. Recetas/Fórmulas
Definición de recetas con lista de materiales, tiempos de fabricación y cálculo automático de costos.

### 4. Costos de Producción
Análisis detallado con desglose: materia prima, empaque, mano de obra, administrativos, indirectos.

### 5. CRM Clientes
Base de datos completa de clientes con historial de compras, saldos pendientes y categorización.

### 6. Cotizaciones
Creación de cotizaciones profesionales, seguimiento y conversión automática a pedidos.

### 7. Pedidos
Registro automático de pedidos, generación de órdenes de producción y actualización de inventario.

### 8. Ventas
Registro de ventas realizadas, facturas en PDF y descuento automático de inventario.

### 9. Ingresos
Registro centralizado de todos los ingresos con proyecciones financieras.

### 10. Egresos/Gastos
Clasificación detallada de gastos por categoría con comparativos presupuestarios.

### 11. Dashboard Financiero
Indicadores clave: ingresos/egresos, balance, márgenes, tendencias y salud financiera.

### 12. Reportes y Estadísticas
Reportes exportables en Excel/PDF con análisis de rentabilidad, flujo de caja, etc.

## 🔐 Seguridad

- Autenticación JWT con tokens con expiración
- Encriptación de datos sensibles
- Validación de entrada en todos los endpoints
- CORS configurado
- Rate limiting implementado
- Auditoría de cambios en registros importantes

## 📱 Responsive Design

Diseño completamente adaptable:
- **Desktop** (1200px+): Vista completa con sidebar
- **Tablet** (768px-1199px): Menú colapsable
- **Móvil** (<768px): Navegación tipo hamburguesa

## 🌙 Modo Oscuro

Disponible en configuración de usuario, con persistencia automática de preferencia.

## 💾 Datos Locales

Uso de IndexedDB para funcionamiento offline con sincronización automática cuando hay conexión.

## 📊 Exportación de Datos

- **Excel** (.xlsx) - Para análisis en hojas de cálculo
- **PDF** - Para reportes profesionales
- **CSV** - Para importación en otros sistemas

## 🔧 Configuración del Negocio

Personalizable según necesidades:
- Porcentaje costos administrativos (default: 20%)
- Porcentaje costos indirectos (default: 20%)
- Margen de utilidad (default: 80%)
- Datos empresa: nombre, NIT, dirección, logo
- Moneda: COP (pesos colombianos)

## 📞 Soporte

Para problemas o sugerencias, contactar al equipo de desarrollo.

## 📄 Licencia

Todos los derechos reservados © 2024 Mini Ramo Flores

---

**Versión**: 1.0.0  
**Última actualización**: 2024
