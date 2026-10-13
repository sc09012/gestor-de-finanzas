# NexFinance · Gestor de Finanzas

**Terminal de control financiero personal** para registrar ingresos y gastos, visualizar el balance mensual, analizar conceptos con un gráfico interactivo y exportar un reporte profesional en PDF.

![Licencia](https://img.shields.io/badge/licencia-MIT-blue)
![Plataforma](https://img.shields.io/badge/plataforma-Windows%20%7C%20macOS%20%7C%20Web-38bdf8)
![Versión](https://img.shields.io/badge/versión-1.0.0-4ade80)
[![Web](https://img.shields.io/badge/Web-En_línea-38bdf8)](https://sc09012.github.io/gestor-de-finanzas/)

---

## Landing page · Propósito y uso

Visita la **[landing page](https://sc09012.github.io/gestor-de-finanzas/)** para conocer el **propósito de la app** y el **modo de usarla** paso a paso.

Ahí encontrarás:

- **Abrir la aplicación**: usarla directamente en el navegador.
- **Descargar HTML**: obtener el archivo suelto para abrirlo con doble clic.
- **Descargar Windows (.exe)**: acceder a los instaladores publicados en las Releases.
- **Guía de uso**: explicación de cada función (ingresos, gastos, balance, gráfico y PDF).

> Landing: `https://sc09012.github.io/gestor-de-finanzas/`

---

## Tabla de contenido

- [Landing page · Propósito y uso](#landing-page--propósito-y-uso)
- [Características](#características)
- [Cómo funciona](#cómo-funciona)
- [Capturas y acceso rápido](#capturas-y-acceso-rápido)
- [Descargar y usar](#descargar-y-usar)
  - [Opción 1 · Usarlo en línea (GitHub Pages)](#opción-1--usarlo-en-línea-github-pages)
  - [Opción 2 · Descargar el HTML](#opción-2--descargar-el-html)
  - [Opción 3 · Descargar el ejecutable de Windows (.exe)](#opción-3--descargar-el-ejecutable-de-windows-exe)
  - [Opción 4 · Ejecutar desde el código fuente](#opción-4--ejecutar-desde-el-código-fuente)
- [Exportar el reporte en PDF](#exportar-el-reporte-en-pdf)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Compilar ejecutables (.exe y .dmg)](#compilar-ejecutables-exe-y-dmg)
- [Publicar en GitHub Pages](#publicar-en-github-pages)
- [Tecnologías](#tecnologías)
- [Privacidad](#privacidad)
- [Licencia](#licencia)

---

## Características

- **Balance mensual**: selector de mes y año para titular cada balance.
- **Ingresos y gastos**: filas dinámicas e ilimitadas con concepto y monto.
- **Cálculo en tiempo real**: totales de ingresos, gastos y balance neto al instante.
- **Diagnóstico financiero**: detecta **superávit** o **déficit** con alertas de color.
- **Gráfico interactivo (dona)**: distribución por concepto, con porcentajes al pasar el cursor.
- **Formato de moneda automático** (`es-CO`).
- **Exportación a PDF**: reporte con el mes del balance y todos los movimientos.
- **Multiplataforma**: navegador web, aplicación de escritorio para Windows y macOS.

---

## Cómo funciona

NexFinance está construido como una **aplicación web de un solo archivo** (`nexfinance_mvp_fecha.html`):

- **Interfaz y lógica** dentro del propio HTML (JavaScript puro).
- **Estilos** con [Tailwind CSS](https://tailwindcss.com/) (CDN).
- **Gráficos** con [Chart.js](https://www.chartjs.org/) (CDN).
- **Exportación PDF** con [html2pdf.js](https://ekoopmans.github.io/html2pdf.js/) (CDN).

Para la **versión de escritorio**, el HTML se envuelve con [Electron](https://www.electronjs.org/) y se empaqueta con [electron-builder](https://www.electron.build/). El archivo `main.js` abre el HTML en una ventana nativa.

> La aplicación requiere **conexión a internet** para cargar las librerías (CDN). No requiere internet para tu captura de datos, salvo la carga inicial de recursos.

---

## Capturas y acceso rápido

| Recurso | Enlace |
| --- | --- |
| Aplicación en línea (GitHub Pages) | `https://sc09012.github.io/gestor-de-finanzas/` |
| Ejecutable para Windows | `https://github.com/sc09012/gestor-de-finanzas/releases/latest` |
| Repositorio | `https://github.com/sc09012/gestor-de-finanzas` |

---

## Descargar y usar

Tienes cuatro formas de usarlo. Elige la que te resulte más cómoda.

### Opción 1 · Usarlo en línea (GitHub Pages)

No instala nada. Abre en tu navegador:

```
https://sc09012.github.io/gestor-de-finanzas/
```

Pulsa **Abrir la aplicación** y empieza a registrar tus movimientos.

### Opción 2 · Descargar el HTML

Ideal si quieres el archivo suelto para abrirlo con doble clic:

1. Entra al repositorio y abre `nexfinance_mvp_fecha.html`.
2. Pulsa el botón **Download raw file** (o descarga desde la landing, botón **Descargar HTML**).
3. Abre el archivo descargado con tu navegador.

También puedes descargarlo directo:

```
https://github.com/sc09012/gestor-de-finanzas/raw/main/nexfinance_mvp_fecha.html
```

### Opción 3 · Descargar el ejecutable de Windows (.exe)

1. Ve a la sección **Releases** del repositorio.
2. Descarga uno de estos archivos:
   - `NexFinance Setup 1.0.0.exe` → **instalador** (crea accesos directos en el escritorio y el menú de inicio).
   - `NexFinance 1.0.0.exe` → **versión portable** (se ejecuta sin instalar).
3. Ábrelo con doble clic.

> En la primera ejecución, Windows SmartScreen puede mostrar una advertencia porque el ejecutable no está firmado digitalmente. Selecciona *Más información* → *Ejecutar de todas formas*.

### Opción 4 · Ejecutar desde el código fuente

Requisitos: [Node.js 18+](https://nodejs.org/).

```bash
# 1. Clona el repositorio
git clone https://github.com/sc09012/gestor-de-finanzas.git
cd gestor-de-finanzas

# 2. Instala las dependencias
npm install

# 3. Ejecuta la aplicación de escritorio
npm start
```

---

## Exportar el reporte en PDF

Dentro de la aplicación:

1. Pulsa el botón **Exportar Reporte** (arriba a la derecha).
2. La app prepara una versión limpia del balance (oculta botones y reemplaza los campos por texto).
3. Se genera y descarga automáticamente un archivo llamado:

   ```
   Balance_financiero_<mes>_<año>.pdf
   ```

El PDF incluye el título con el **mes y año** del balance, los paneles de ingresos y gastos, el diagnóstico (ingresos, gastos y balance neto) y el gráfico, en tamaño **A4 vertical**.

> Nota: los conceptos y montos se guardan **en memoria** mientras la pestaña/ventana permanece abierta. **Cierra sin guardar de otro modo** implica perder los datos. Exportar el PDF es la forma de conservar un registro.

---

## Estructura del proyecto

```
gestor-de-finanzas/
├── .github/
│   └── workflows/
│       ├── pages.yml              # Publica la landing y la app en GitHub Pages
│       └── release.yml            # Compila el .exe y publica una Release al etiquetar
├── index.html                     # Landing page (GitHub Pages)
├── nexfinance_mvp_fecha.html      # Aplicación (HTML + JS + estilos)
├── main.js                        # Proceso principal de Electron
├── package.json                   # Dependencias y configuración de empaquetado
├── .gitignore                     # Excluye node_modules, dist, etc.
└── README.md
```

---

## Compilar ejecutables (.exe y .dmg)

```bash
npm install          # Instala dependencias (solo la primera vez)

npm run dist         # Genera el .exe para Windows  -> carpeta dist/
npm run dist:mac     # Genera el .dmg para macOS    -> REQUIERE un Mac
```

Los artefactos se generan en `dist/`:

- `NexFinance Setup 1.0.0.exe` (instalador)
- `NexFinance 1.0.0.exe` (portable)
- `NexFinance-1.0.0.dmg` (macOS, solo al compilar en un Mac)

> **Importante:** el `.dmg` de macOS **no se puede generar desde Windows**; debe compilarse en un equipo macOS (o en un runner `macos-latest` de GitHub Actions).

**Publicar el .exe automáticamente**: crea y sube una etiqueta de versión y GitHub Actions compilará y publicará el ejecutable en Releases.

```bash
git tag v1.0.0
git push origin v1.0.0
```

---

## Publicar en GitHub Pages

El workflow `.github/workflows/pages.yml` despliega automáticamente la landing (`index.html`) y la app en cada push a `main`.

Para activarlo la primera vez:

1. Sube el repositorio a GitHub.
2. Ve a **Settings → Pages**.
3. En **Source**, elige **GitHub Actions**.
4. Espera a que termine el workflow en la pestaña **Actions**.
5. Tu sitio estará en `https://sc09012.github.io/gestor-de-finanzas/`.

---

## Tecnologías

| Capa | Herramienta |
| --- | --- |
| Interfaz | HTML5 + Tailwind CSS |
| Lógica | JavaScript (vanilla) |
| Gráficos | Chart.js |
| PDF | html2pdf.js |
| Escritorio | Electron + electron-builder |
| CI/CD | GitHub Actions |

---

## Privacidad

Todos los datos se procesan **localmente** en tu dispositivo. No hay servidores, cuentas ni envío de información: al cerrar la aplicación los datos de la sesión se descartan.

---

## Licencia

Distribuido bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
