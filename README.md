# Look Clock ⌚🏔️

Un avanzado creador de fondos de pantalla animados (Live Wallpapers) para Android construido con Flutter. Permite a los usuarios diseñar, editar y aplicar relojes altamente personalizados que interactúan dinámicamente con el entorno de sus fotografías.

## 🚀 Resumen

**Look Clock** va un paso más allá de la simple personalización de texto. Es un editor visual completo que integra procesamiento de imágenes en el dispositivo para lograr efectos de profundidad reales (Z-Index). A través de algoritmos de detección de color y herramientas de enmascaramiento interactivo, los usuarios pueden colocar el reloj *detrás* de elementos del paisaje (como montañas o edificios) o sumergirlo bajo efectos de agua dinámicos.

## ✨ Características Principales

* **🎨 Motor Tipográfico Avanzado:** Soporte para estiramiento de fuentes (X/Y), desenfoque tipo *Glassmorphism*, brillos de neón interactivos, contornos y sombras paramétricas.
* **⛰️ Máscaras de Profundidad Inteligentes:** Generación automática de máscaras PNG a partir de la imagen base. Utiliza un algoritmo de escaneo de píxeles (*flood-fill*) que evalúa la luminosidad y tolerancia de color para detectar cielos y separar el fondo del paisaje.
* **🖌️ Goma de Borrar de Precisión:** Herramienta interactiva de edición en lienzo libre. Permite borrar partes específicas del reloj con soporte de interpolación de trazos y un sistema completo de Deshacer/Rehacer.
* **🌊 Motor de Efectos Ambientales:** Integración de capa de agua con recortes horizontales matemáticos, opacidad de líneas de flotación y mezcla de reflejos.
* **🔗 Ecosistema de Exportación:** Guarda configuraciones complejas localmente o compártelas externamente. Genera esquemas JSON comprimidos mediante `zlib` que se pueden importar mediante archivos o *Deep Links* (`lookclock://import`).

## 🛠️ Stack Tecnológico y Flujo de Desarrollo

* **Framework:** Flutter (Dart) con puente nativo `MethodChannel` para la implementación del servicio Live Wallpaper en Android.
* **Procesamiento de Imágenes:** Paquete `image` para la decodificación de bytes en bruto, generación de máscaras alfa e interpolación de recortes.
* **Gestión de Estado:** Sistema reactivo apoyado en el ciclo de vida del *SchedulerBinding* y una pila de instantáneas (`_EditorSnapshot`) circular para gestionar el historial de Deshacer/Rehacer.
* **Almacenamiento Local:** `shared_preferences` para configuraciones de interfaz ligeras y retención de proyectos "Look".
* **Gestión de Archivos y Compartición:** Manipulación profunda de archivos mediante `path_provider`, combinada con compresión Base64+Zlib para el sistema de Deep Linking a través de `share_plus`.

## 📱 Escaparate de la App e Interfaz de Edición

A diferencia de un reloj superpuesto tradicional, Look Clock permite jugar con la refracción del entorno y la luz interactiva a través de su motor de edición.

<table width="100%" cellspacing="0" cellpadding="0">
  <tr>
    <td width="50%" align="center" valign="top">
      <b>🌊 Efecto Inmersión Dinámico</b>
    </td>
    <td width="50%" align="center" valign="top">
      <b>✨ Motor Tipográfico Avanzado</b>
    </td>
  </tr>
  <tr>
    <td valign="top" align="center">
      <p align="center"><i>Corte matemático del lienzo y opacidad de línea de flotación para simular hundimiento y refracción.</i></p>
      <img src="asset/videos/efecto_inmersion.gif" width="90%">
    </td>
    <td valign="top" align="center">
      <p align="center"><i>Renderizado nativo con shaders interactivos para efectos de Cristal (Glassmorphism) y Neón.</i></p>
      <img src="asset/videos/motor_tipografico.gif" width="90%">
    </td>
  </tr>
</table>
<br>

<table width="100%" cellspacing="0" cellpadding="0">
  <tr>
    <td width="50%" align="center" valign="top">
      <b>⛰️ Profundidad de Campo (Máscara Inteligente)</b>
    </td>
    <td width="50%" align="center" valign="top">
      <b>🖌️ Goma de Borrar de Precisión</b>
    </td>
  </tr>
  <tr>
    <td valign="top" align="center">
      <p align="center"><i>Algoritmo de escaneo de píxeles (flood-fill) para detectar el cielo y ocultar el reloj tras el paisaje.</i></p>
      <img src="asset/videos/profundidad_de_campo.gif" width="90%">
    </td>
    <td valign="top" align="center">
      <p align="center"><i>Edición en lienzo libre con soporte de interpolación de trazos para ajustes de máscara milimétricos.</i></p>
      <img src="asset/videos/goma_interactiva.gif" width="90%">
    </td>
  </tr>
</table>

<br>

<br>

## 🖼️ Galería de Resultados (Looks)

Una pequeña muestra de lo que se puede llegar a crear combinando las herramientas de profundidad, fuentes y efectos de renderizado.

<table width="100%" cellspacing="0" cellpadding="0">
  <tr>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_0.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_1.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_2.jpeg" width="95%">
    </td>
  </tr>
  <tr>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_3.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_4.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_5.jpeg" width="95%">
    </td>
  </tr>
  <tr>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_6.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_7.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_8.jpeg" width="95%">
    </td>
  </tr>
  <tr>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_9.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_10.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_11.jpeg" width="95%">
    </td>
  </tr>
  <tr>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_12.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_13.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_14.jpeg" width="95%">
    </td>
  </tr>
  <tr>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_15.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_16.jpeg" width="95%">
    </td>
    <td width="33.3%" align="center" valign="top">
      <img src="asset/images/galeria_17.jpeg" width="95%">
    </td>
  </tr>
</table>