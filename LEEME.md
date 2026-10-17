# AGameX en Vercel — pasos

Esta carpeta es la tienda completa. Los productos se crean y editan desde la propia web
(Acceder → usuario `akiles` + tu contraseña) y se guardan en una base de datos gratuita.

## 1. Subir el proyecto
1. Sube la carpeta `vercel-store` a un repositorio de GitHub (o usa `vercel` desde la terminal dentro de la carpeta).
2. En vercel.com → **Add New → Project** → elige ese repositorio.
3. Framework Preset: **Other**. No hace falta tocar nada más. Pulsa **Deploy**.

## 2. Conectar la base de datos (gratis)
1. En tu proyecto de Vercel: **Storage → Create Database / Marketplace → Upstash (Redis)** → plan gratis → **Connect to Project**.
2. Eso añade solo las variables `KV_REST_API_URL` y `KV_REST_API_TOKEN` (o `UPSTASH_REDIS_REST_URL` y `UPSTASH_REDIS_REST_TOKEN`).

## 3. Poner tu contraseña de propietario
1. **Settings → Environment Variables** → añade `ADMIN_PASSWORD` con la contraseña que quieras.
2. (Opcional) añade `SESSION_SECRET` con cualquier texto largo y aleatorio.
3. **Deployments → Redeploy** para que se apliquen.

## 4. Usarla
- Abre tu web → **Acceder** → usuario `akiles` y tu `ADMIN_PASSWORD`.
- En el panel: **＋ Añadir producto**. Cada producto tiene Sección (Productos / Juegos), Colección, precio, stock, descripción, variantes e imagen.
- Todo se guarda solo y lo ven tus clientes al momento (los visitantes se refrescan cada minuto).

## Notas
- Para cambiar la contraseña: cambia `ADMIN_PASSWORD` en Vercel y haz Redeploy.
- Las imágenes subidas desde el panel se reducen mucho para caber en la base de datos. Si vas a tener muchos productos, pega **enlaces de imagen** (https://...) en vez de subirlas.
- Si cambias el diseño en `index.html` (carpeta de arriba), ejecuta `node build-vercel.js` para regenerar esta carpeta.
