# Controla — panel de inventario

Panel React listo para Vercel y Firestore. Cada producto se almacena en `products` y cada venta en `sales`; al registrar una venta se actualiza el stock mediante una transacción atómica.

## Puesta en marcha

1. Crea un proyecto de Firebase, habilita **Cloud Firestore** y copia la configuración web en `.env` usando `.env.example`.
2. Ejecuta `npm install` y `npm run dev`.
3. Sube este directorio a GitHub e impórtalo en Vercel. Añade las mismas variables `VITE_FIREBASE_*` en **Project Settings → Environment Variables**.

Para el primer uso de Firestore durante desarrollo puedes utilizar estas reglas (antes de publicar, activa Authentication y restrínge las reglas):

```js
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} { allow read, write: if true; }
  }
}
```

Coloca la imagen de la tienda en `src/assets/logo-placeholder.svg` y sustitúyela cuando tengas tu logo.
