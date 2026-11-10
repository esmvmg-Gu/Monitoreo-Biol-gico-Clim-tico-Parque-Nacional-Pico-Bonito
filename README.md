# Monitoreo Biológico-Climático · Parque Nacional Pico Bonito

Tablero interactivo con los resultados del monitoreo de vegetación y aves del Parque Nacional Pico Bonito (Atlántida, Honduras), 2023–2026. Lo elaboró la Fundación Parque Nacional Pico Bonito (FUPNAPIB).

Incluye:

- Portada e introducción con la metodología.
- Mapa de parcelas sobre imagen satelital, con las zonas Núcleo y Amortiguamiento.
- Indicadores de riqueza, diversidad (Shannon, Simpson), IVI, estructura diamétrica, persistencia y crecimiento del DAP.
- Conteos y curvas de acumulación de aves.
- Registro de especies con búsqueda.

Funciona en computadora y en celular.

## Contenido del repositorio

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El tablero completo. Datos, logos y figuras van incluidos en el mismo archivo. |
| `.nojekyll` | Hace que GitHub Pages publique el archivo tal cual, sin procesarlo. |
| `README.md` | Este documento. |

## Publicar con GitHub Pages

1. En GitHub, cree un repositorio nuevo, por ejemplo `pnpb-monitoreo`. Puede ser público o privado; GitHub Pages en repositorios privados requiere un plan de pago.
2. Suba los tres archivos con **Add file → Upload files** y confirme con **Commit changes**. `.nojekyll` es un archivo oculto: si su computadora no lo muestra, puede omitirlo.
3. Vaya a **Settings → Pages**.
4. En **Build and deployment**, elija **Source: Deploy from a branch**, rama **main** y carpeta **/ (root)**. Guarde.
5. Espere uno o dos minutos. La dirección aparece en la misma página, con esta forma:
   `https://SU-USUARIO.github.io/pnpb-monitoreo/`

Si prefiere la terminal:

```bash
git init
git add index.html README.md .nojekyll
git commit -m "Tablero de monitoreo PNPB 2023-2026"
git branch -M main
git remote add origin https://github.com/SU-USUARIO/pnpb-monitoreo.git
git push -u origin main
```

## Requisitos

- Conexión a internet para cargar la librería D3, las fuentes y la imagen satelital (Esri World Imagery). Sin conexión, el mapa se muestra sin fondo y las gráficas siguen funcionando si D3 ya está en la caché del navegador.
- Cualquier navegador moderno: Chrome, Edge, Firefox o Safari, en computadora o celular.

## Uso en el celular

- La barra superior queda fija. El botón **Filtros** abre y cierra el sector y el umbral de DAP.
- En el mapa, un dedo desplaza la página. Use **dos dedos** para mover y acercar el mapa, o los botones **+** y **−**.
- Toque una parcela o una barra para ver la ficha de esa parcela.
- El botón **Leyenda** muestra u oculta la leyenda del mapa.

## Fuentes de datos

- *Monitoreo Biológico-Climático del PNPB 2023–2026* (libro de Excel con los datos crudos de vegetación y aves de los sectores norte y sur).
- *Límites de Zonas del PNPB* (Decreto Legislativo 87-87), reproyectados de UTM 16N a WGS 84.
- Imágenes satelitales: Esri, Maxar, Earthstar Geographics.

Los índices se calculan a partir de los datos crudos. Los nombres de especies están unificados y los árboles con mediciones dudosas aparecen marcados en la ficha de cada parcela. Los detalles de método están en el pie de página del tablero.

## Cómo citar

Fundación Parque Nacional Pico Bonito (FUPNAPIB). 2026. *Monitoreo Biológico-Climático del Parque Nacional Pico Bonito, 2023–2026*. Tablero interactivo de resultados.

## Actualizar los datos

Los datos van incluidos en `index.html`, dentro de la etiqueta `<script type="application/json" id="data">`. Para nuevas remediciones o conteos, lo más sencillo es regenerar el tablero desde el Excel actualizado.
