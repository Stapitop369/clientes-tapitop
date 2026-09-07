# Clientes — Studio Tapitop

App para iPhone del equipo comercial: cada vendedor registra nombre, teléfono, correo, vendedor y comentarios del cliente, y al pulsar **Enviar** los datos llegan por correo a `alonso.rodriguez@studiotapitop.com`.

Es una web app instalable (PWA), igual que la Calculadora: no necesita App Store ni cuenta de desarrollador. Sigue el Brand Book (paleta negro/taupe/crema, Arual + Generica, lockup horizontal, etiqueta cosida, hilván).

## Instalar en cada iPhone

1. Abrir el enlace en Safari.
2. Tocar **Compartir** → **Añadir a pantalla de inicio**.
3. La app queda con el icono de Studio Tapitop y se abre sin barra del navegador.

## Activar el correo (una sola vez)

Los envíos usan [FormSubmit](https://formsubmit.co). La primera vez que alguien envía un registro, `alonso.rodriguez@studiotapitop.com` recibe un correo de FormSubmit con un botón **Activate form**. Hay que pulsarlo una vez; desde entonces cada registro llega como un correo con una tabla de datos y el asunto `Nuevo cliente · Nombre · Vendedor`.

Opcional: tras activar, FormSubmit ofrece un identificador aleatorio que sustituye al correo en la URL. Si se quiere que el correo no aparezca en el código, cambia `RECIPIENT` en `index.html` por ese identificador.

## Si no hay conexión

El registro se guarda en el teléfono como **Pendiente** y se reenvía solo cuando vuelve la conexión (o con el botón **Reintentar pendientes**). También aparece **Enviar por correo**, que abre Mail con todo rellenado. La lista *Registros en este dispositivo* muestra los últimos 200 envíos de ese teléfono.

## Cambiar el destinatario o los campos

- Destinatario: constante `RECIPIENT` al inicio del `<script>`.
- Campos: cada bloque `.field` del formulario y la lista `fields` del script. Los nombres que se ven en el correo están en la función `send()`.
- Vendedores: el campo recuerda los nombres ya usados en ese teléfono y propone el último; no hay lista fija que mantener.

## Publicar

Copiar la carpeta al hosting (o GitHub Pages). Todo es estático: `index.html`, `manifest.json` y los iconos.
