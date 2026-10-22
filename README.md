# Explorador

Explorador de archivos para Linux, hecho con GTK4 y Rust. Pensado para KDE Plasma sobre Wayland, aunque funciona en otros escritorios que tengan GTK4.

Este repositorio solo contiene los ejecutables. En la pestaña **Releases** está siempre la última versión.

## Qué hace

**Navegación**
- Pestañas, que se pueden arrastrar a una ventana propia y volver a unir.
- Vista de lista y de grilla, con zoom usando Ctrl y la rueda del mouse.
- Pantalla dividida con dos paneles independientes.
- Barra de ruta con migas de pan que se puede editar escribiendo o pegando una ruta.
- Barra lateral con carpetas del usuario, marcadores y unidades montadas.
- Búsqueda por nombre y por contenido, en la carpeta actual o en subcarpetas. Ignora mayúsculas y acentos, acepta varias palabras y comodines como `*.png`.

**Archivos**
- Copiar, cortar, pegar y arrastrar y soltar, con barra de progreso y botón para cancelar.
- Papelera real, con restaurar y vaciar.
- Renombrado en el mismo lugar, renombrado en lote y deshacer de la última acción.
- Selección múltiple con Ctrl, Shift y arrastrando sobre el espacio vacío.
- Comprimidos (zip, 7z, tar y otros) que se recorren como carpetas.
- Detección de carpetas sin permiso, marcadas con un candado.

**Organización**
- Notas en cualquier archivo o carpeta.
- Archivos relacionados agrupados bajo uno principal, por ejemplo un `.blend` con sus copias de seguridad o un mapa de texturas con su base. Las reglas se pueden editar.
- Ocultar archivos y carpetas sin cambiar su nombre.
- Vista simple, que esconde lo que no hace falta ver en Descargas y muestra debajo las aplicaciones y juegos instalados de Steam, Heroic, Flatpak y AppImage.
- Renombrar los accesos de aplicaciones instaladas sin tocar el paquete original.
- Iconos propios por carpeta o archivo, y temas de iconos editables.

**Vista previa y detalles**
- Miniaturas de imágenes, videos, portadas de audio y archivos de Blender.
- Imágenes AVIF, WebP, HEIC, SVG, RAW de cámara y muchos otros formatos, si están instaladas las herramientas opcionales.
- Vista previa rápida con la barra espaciadora.
- Propiedades en pestañas: general, permisos, sumas de verificación y detalles propios de cada tipo de archivo.

**Herramientas**
- Buscador de archivos duplicados.
- Analizador de espacio en disco.
- Abrir una terminal en la carpeta actual.
- Si es tu explorador predeterminado, la opción "Mostrar en la carpeta" de otras aplicaciones (navegadores, Discord, Steam y similares) abre una pestaña en Explorador.
- Preferencias para el tema, la carpeta de inicio, las confirmaciones de borrado y la búsqueda.

## Requisitos

- Linux de 64 bits con GTK 4.10 o más nuevo.
- Compilado en CachyOS (Arch). En distribuciones más antiguas puede no arrancar por la versión de las bibliotecas del sistema.

Herramientas opcionales. Si faltan, la función correspondiente simplemente no aparece:

| Herramienta | Para qué sirve |
|---|---|
| `p7zip` (`7z`) | Recorrer y modificar comprimidos |
| `ffmpeg`, `ffmpegthumbnailer` | Miniaturas de video y de formatos de imagen poco comunes |
| `imagemagick` | Miniaturas de PSD, TIFF, RAW y otros |
| `librsvg` (`rsvg-convert`) | Miniaturas de SVG |
| `libavif` (`avifdec`) | Miniaturas de AVIF |
| `exiv2` | Datos EXIF de fotos |
| `poppler` (`pdfinfo`) | Datos de archivos PDF |

En Arch y derivadas:

```bash
sudo pacman -S p7zip ffmpeg ffmpegthumbnailer imagemagick librsvg libavif exiv2 poppler
```

## Instalación

1. Descargá `explorador-gtk-linux-x86_64.tar.gz` desde la última release.
2. Extraelo y ejecutá el instalador:

```bash
mkdir explorador && tar -xzf explorador-gtk-linux-x86_64.tar.gz -C explorador
cd explorador
./instalar.sh
```

El instalador no pide permisos de administrador. Copia el programa a `~/.local/bin`, registra el ícono y agrega "Explorador" al menú de aplicaciones.

Para usarlo como explorador predeterminado y con el atajo Meta+E (solo KDE Plasma), abrí **Preferencias, Sistema, Explorador predeterminado**.

## Actualizar

Dentro de la app: **Preferencias, Sistema, Buscar actualizaciones**. Compara tu versión con la última publicada, la descarga y se reinicia sola.

## Desinstalar

Desde la carpeta extraída:

```bash
./desinstalar.sh
```

Los datos de la app (notas, marcadores, preferencias) quedan en `~/.local/share/explorador`. Podés borrar esa carpeta si no los querés conservar.

## Problemas y sugerencias

Se pueden abrir desde la pestaña **Issues** de este repositorio.
