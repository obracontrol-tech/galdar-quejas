# 🗳️ Quejas Vecinales Gáldar
### App PWA para José Blas Díaz Bolaños — Unidos por Gran Canaria

---

## 📁 Archivos del proyecto

```
galdar-quejas/
├── index.html        ← App principal
├── style.css         ← Estilos
├── manifest.json     ← Config PWA
├── sw.js             ← Service Worker (offline)
├── logo.png          ← Logo Unidos por Gran Canaria
└── firestore.rules   ← Reglas de seguridad Firebase
```

---

## 🚀 GUÍA DE DESPLIEGUE PASO A PASO

### PASO 1 — Crear proyecto Firebase

1. Ve a https://console.firebase.google.com
2. Pulsa **"Crear un proyecto"**
3. Nombre: `galdar-quejas`
4. Desactiva Google Analytics (no hace falta)
5. Pulsa **"Crear proyecto"**

### PASO 2 — Activar Firestore

1. En el menú izquierdo: **Compilación → Firestore Database**
2. Pulsa **"Crear base de datos"**
3. Selecciona **modo de producción**
4. Región: `europe-west` (más cercana a Canarias)
5. Pulsa **"Listo"**

### PASO 3 — Copiar la configuración Firebase

1. En Firebase Console → ⚙️ Configuración del proyecto → **"Tus apps"**
2. Pulsa el icono **`</>`** (web)
3. Nombre de la app: `galdar-quejas-web`
4. **NO** actives Firebase Hosting
5. Copia el objeto `firebaseConfig` que aparece

### PASO 4 — Pegar la config en index.html

Abre `index.html` y busca este bloque (cerca del final):

```javascript
const firebaseConfig = {
  apiKey: "TU_API_KEY",
  authDomain: "TU_PROJECT.firebaseapp.com",
  ...
```

Sustitúyelo por los datos reales que copiaste en el paso 3.

### PASO 5 — Cambiar la contraseña del concejal

En `index.html` busca esta línea y cambia la contraseña:

```javascript
const PIN_CONCEJAL = "galdar2025";
```

Pon una contraseña segura que solo sepa José Blas.

### PASO 6 — Aplicar reglas de seguridad Firestore

1. En Firebase Console → Firestore → **Reglas**
2. Borra el contenido actual
3. Copia y pega el contenido de `firestore.rules`
4. Pulsa **"Publicar"**

### PASO 7 — Subir a GitHub Pages

1. Ve a https://github.com/jmplleida
2. Crea un repositorio nuevo llamado `galdar-quejas`
3. Súbelo como público
4. Sube todos estos archivos:
   - index.html
   - style.css
   - manifest.json
   - sw.js
   - logo.png
5. Ve a **Settings → Pages**
6. Source: **Deploy from a branch**
7. Branch: **main**, carpeta: **/ (root)**
8. Guarda

La app estará en: **https://jmplleida.github.io/galdar-quejas/**

---

## 🔑 Contraseña del panel concejal

Cambia `galdar2025` por la que decidas en el `index.html`.
Solo José Blas debe saberla.

---

## 📲 Instalar como app en el móvil

1. Abrir la URL en Chrome (Android) o Safari (iPhone)
2. Pulsar los tres puntos → **"Añadir a pantalla de inicio"**
3. Se instala como una app nativa

---

## ✏️ Personalización futura

- **Cambiar barrios**: editar las opciones del `<select id="barrio">` en index.html
- **Cambiar categorías**: editar el `<select id="categoria">`
- **Cambiar contraseña**: buscar `PIN_CONCEJAL` en index.html
