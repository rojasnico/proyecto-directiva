# Panel de la Directiva de Curso

Página para planificar eventos y administrar los fondos de la directiva.
Está publicada en GitHub Pages y conectada a una base de datos en Supabase.

## Dirección pública

```
https://rojasnico.github.io/proyecto-directiva/
```

## Cómo se entra (login)

El acceso es con **cuenta personal** (email + contraseña) mediante Supabase Auth.
Ya no hay un código compartido. Solo las personas con cuenta pueden ver y editar
los datos: sin iniciar sesión, la base de datos no entrega nada.

Cada cambio queda registrado con el nombre de quien lo hizo.

### Miembros con cuenta
- María Jesús Retamal — mjretama@gmail.com
- Carlos Donoso — carlosdonosog@yahoo.com
- Edwin Rojas — edwin.nr.galvez@gmail.com

La contraseña inicial de todas las cuentas es la misma; pídela por interno y
cámbiala apenas entres (ver más abajo).

## Agregar un nuevo miembro

Se crea su cuenta en Supabase (panel del proyecto **directiva-curso** →
**Authentication** → **Add user**), con email, contraseña y "Auto Confirm".
Listo, ya puede entrar.

## Cambiar la contraseña

Desde el panel de Supabase: **Authentication** → selecciona el usuario →
**Reset password / Update**. (Más adelante se puede agregar un botón de
"cambiar contraseña" dentro de la propia página.)

## Seguridad

- La llave de Supabase dentro del `index.html` es **pública por diseño**: es
  normal que quede a la vista. Lo que protege los datos es el inicio de sesión
  y las reglas de acceso (RLS), no la llave.
- Las tablas `eventos` y `destinos` solo permiten lectura/escritura a usuarios
  **autenticados**. Sin login, nadie accede.
- Los datos se comparten en vivo entre todos los que tengan cuenta.

## Actualizar las finanzas (sección Finanzas)

La pestaña **Finanzas** se arma a partir del archivo `finanzas.json`, que se genera
desde el Excel de tesorería con un script.

Cuando tengas un Excel nuevo:

```
python build_finanzas.py "ruta/al/tesoreria_apoderados.xlsx"
git add finanzas.json
git commit -m "Actualizar finanzas"
git push
```

(Requiere `pip install openpyxl` la primera vez.) Los datos se publican en ~1 minuto.
El Excel original **no** se sube al repositorio, solo el `finanzas.json` resultante.

## Actualizar la página

Editar los archivos y luego:

```
git add -A
git commit -m "tu mensaje"
git push
```

Los cambios se reflejan en la dirección pública en ~1 minuto.
