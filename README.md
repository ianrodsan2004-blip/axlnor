# Axinop — panel de inventario

Aplicación React/Vite lista para desplegar en Vercel. Los productos se guardan en la colección `products` y las ventas en `sales` de Cloud Firestore.

## Desplegar en Vercel

1. Sube esta carpeta a un repositorio de GitHub (sin `.env` ni `node_modules`).
2. En [Vercel](https://vercel.com/new), selecciona el repositorio e importa el proyecto.
3. En **Environment Variables**, agrega las variables de `.env.example` para Production, Preview y Development:

   - `VITE_FIREBASE_API_KEY`
   - `VITE_FIREBASE_AUTH_DOMAIN`
   - `VITE_FIREBASE_PROJECT_ID`
   - `VITE_FIREBASE_STORAGE_BUCKET`
   - `VITE_FIREBASE_MESSAGING_SENDER_ID`
   - `VITE_FIREBASE_APP_ID`

4. Pulsa **Deploy**. Vercel usará `npm run build` y publicará la carpeta `dist` automáticamente.

## Firebase

En Firebase habilita **Cloud Firestore**. La configuración se toma únicamente desde las variables de entorno de Vercel o desde un `.env` local basado en `.env.example`.

Antes de publicar, activa Firebase Authentication y aplica reglas de Firestore que permitan leer y escribir solo a usuarios autorizados. No publiques reglas abiertas como `allow read, write: if true`.

## Desarrollo local

```bash
npm install
npm run dev
```
