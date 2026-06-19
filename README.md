# Panel de la Directiva de Curso — Publicar en GitHub Pages

Esta página ya está conectada a la base de datos. Solo falta subirla a GitHub
y activar GitHub Pages para que tenga una dirección pública y gratuita.

## Paso a paso (unos 5 minutos)

### 1. Crea una cuenta en GitHub (si no tienes)
Anda a https://github.com y regístrate. Es gratis.

### 2. Crea un repositorio nuevo
- Arriba a la derecha, botón **+** → **New repository**.
- Ponle un nombre, por ejemplo: `directiva-curso`.
- Déjalo en **Public**.
- Marca la casilla **Add a README file** (opcional).
- Botón **Create repository**.

### 3. Sube el archivo `index.html`
- Dentro del repositorio: botón **Add file** → **Upload files**.
- Arrastra el archivo **`index.html`** (el que está en esta misma carpeta).
- Abajo, botón **Commit changes**.

### 4. Activa GitHub Pages
- En el repositorio, anda a **Settings** (la rueda dentada, arriba).
- En el menú de la izquierda, entra a **Pages**.
- En **Source**, elige **Deploy from a branch**.
- En **Branch**, elige **main** y la carpeta **/ (root)**. Botón **Save**.

### 5. Listo
Espera 1–2 minutos y recarga la página de **Settings → Pages**.
Aparecerá tu dirección pública, algo como:

```
https://tu-usuario.github.io/directiva-curso/
```

Comparte ese link y el código de acceso `curso2026` con la directiva.
Funciona desde cualquier navegador, en celular o computador.

## Cambiar el código de acceso
Abre `index.html`, busca esta línea y cámbiala:

```js
const CODIGO_ACCESO = "curso2026";
```

Luego vuelve a subir el archivo (Add file → Upload files → reemplaza).

## Notas
- La llave de Supabase dentro del `index.html` es **pública por diseño**:
  es normal y seguro que quede a la vista en una página estática.
- Cualquiera con el link y el código puede ver y editar (así lo definiste).
  No guardes datos sensibles (RUT, datos de cuentas personales).
- Los datos se comparten en vivo entre todos los que entren.
