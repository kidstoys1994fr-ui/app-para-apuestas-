# chupalooo

App Android sencilla. Escribes la cuota de dos equipos y el total a apostar, y te dice cuánto poner en cada uno (sin el empate) para ganar lo mismo gane quien gane. Funciona sin internet.

## Cómo obtener el APK

1. Crea un repositorio nuevo en GitHub y sube todos los archivos de esta carpeta (incluida la carpeta oculta `.github`).
2. Entra a la pestaña **Actions** del repositorio. Si te pide permiso para activar los workflows, acéptalo.
3. Abre la ejecución **Compilar APK**. Si no arrancó sola, usa **Run workflow**.
4. Cuando termine (unos 3 a 5 minutos), baja a **Artifacts** y descarga **chupalooo-apk**. Es un ZIP que contiene `app-debug.apk`.
5. Pasa el APK al celular y ábrelo. Android pedirá permiso para instalar apps de fuentes desconocidas.

## Estructura

- `app/src/main/assets/index.html`: la calculadora (HTML, CSS y JavaScript).
- `app/src/main/java/.../MainActivity.java`: abre la calculadora dentro de un WebView.
- `.github/workflows/build-apk.yml`: compila el APK automáticamente en GitHub.

Para cambiar algo de la calculadora, edita `index.html` y vuelve a subirlo: GitHub genera un APK nuevo.

## La cuenta

Con cuotas `o1` y `o2` y un total `T`:

- Apuesta a equipo 1: `T × (1/o1) / (1/o1 + 1/o2)`
- Apuesta a equipo 2: lo que queda del total
- Si gana cualquiera recibes `T / (1/o1 + 1/o2)`
- Si hay empate pierdes `T`
