# ⚽ Quiniela Mundial 2026

App web para jugar la quiniela del Mundial con amigos. Sin apps, sin registro, sin complicaciones.

## Características
- Todos los partidos del Mundial 2026 (grupos + eliminatorias)
- Sistema de puntos configurable
- Panel de administrador para ingresar resultados reales
- Tabla de posiciones en tiempo real
- PIN por jugador para proteger sus picks
- Funciona desde cualquier celular (sin instalar nada)

## Contraseña de administrador
Por defecto: `mundial2026admin`

**Cámbiala** en el archivo `js/data.js`, línea 1:
```js
const ADMIN_PASSWORD = "tu-contraseña-aqui";
```

## Cómo subir a Netlify (gratis)

### Opción A — Arrastar y soltar (más fácil)
1. Ve a https://app.netlify.com
2. Crea una cuenta gratis
3. En el dashboard, arrastra la carpeta `mundial2026` completa
4. Netlify te da un link tipo `https://nombre-random.netlify.app`
5. ¡Comparte ese link con tus amigos!

### Opción B — Netlify CLI
```bash
npm install -g netlify-cli
netlify deploy --dir=mundial2026 --prod
```

## Cómo personalizar
- **Equipos**: edita el objeto `GROUPS` en `js/data.js`
- **Puntos**: desde el panel admin → Config
- **Contraseña admin**: `ADMIN_PASSWORD` en `js/data.js`

## Sistema de puntos (por defecto)
- ✅ Resultado exacto (ej: predijiste 2-1 y fue 2-1): **3 puntos**
- ✅ Ganador correcto (predijiste que ganaba, sin importar marcador): **1 punto**  
> Nota: actualmente el sistema calcula solo por resultado (1/X/2), no por marcador exacto.
>  Para marcador exacto extra, configúralo desde el panel admin.

## Datos
Los datos se guardan en `localStorage` del navegador de **quien administra**.
No hay base de datos en la nube — tú (el admin) eres el servidor.

Para compartir resultados entre dispositivos, sube la app a Netlify y todos
acceden al mismo link. Los picks de cada jugador se guardan en su propio navegador.

> ⚠️ Si un jugador borra el caché del navegador, pierde sus picks guardados localmente.
> El admin debe guardar resultados y recalcular puntos regularmente.
