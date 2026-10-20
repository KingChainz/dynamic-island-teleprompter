# 🏝️ Dynamic Island Teleprompter

[![Windhawk Mod](https://img.shields.io/badge/Windhawk-Mod-0078D4?style=for-the-badge&logo=windows&logoColor=white)](https://windhawk.net/)
[![Direct2D / DirectWrite](https://img.shields.io/badge/Renderer-Direct2D%20%2F%20DirectWrite-68217A?style=for-the-badge&logo=c%2B%2B&logoColor=white)](https://learn.microsoft.com/en-us/windows/win32/direct2d/direct2d-portal)
[![Author](https://img.shields.io/badge/Author-0xCh4inz-F5A623?style=for-the-badge)](https://github.com/0xCh4inz)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

Un teleprónter flotante ultraligero y minimalista estilo **Dynamic Island** para Windows 10/11, desarrollado como mod nativo para **[Windhawk](https://windhawk.net/)** con renderizado acelerado por hardware mediante **Direct2D** y **DirectWrite**.

Ubicado justo debajo del marco superior de la pantalla (bajo tu cámara web), te permite leer tus guiones de forma natural manteniendo contacto visual directo con la cámara en llamadas de Zoom/Teams, presentaciones o grabaciones con OBS.

---

## ✨ Características Principales

- 🏝️ **Estética Dynamic Island con Físicas Spring:**
  Animaciones orgánicas fluidas basadas en un oscilador armónico amortiguado (`tension: 210`, `damping: 23`) al expandirse, contraerse o alternar paneles.
- 👁️ **Guía de Contacto Visual (Eye-Line Guide):**
  Línea sutil de referencia visual posicionada a la altura óptima debajo de la lente de tu cámara web.
- 👻 **Modo Fantasma (Click-Through Total):**
  Activa `WS_EX_TRANSPARENT` al pulsar el botón amarillo superior derecho o mediante `Ctrl + Alt + G`. Los clics atraviesan completamente la isla hacia tus aplicaciones de fondo (OBS, PowerPoint, Chrome), permitiéndote operar tu PC sin interrumpir la lectura.
- ⚡ **Panel de Atajos Desplegable e Interactivo:**
  Al pulsar `Ctrl + Alt + X` (o hacer clic en la barra inferior), se despliega una sub-isla con atajos. **Cada fila es clickeable** para ejecutar la acción al instante.
- 🖱️ **Control Dinámico con Rueda de Ratón:**
  Ajusta la velocidad de avance en tiempo real girando la rueda del ratón (`Rueda: Vel(X%)`).
- 📋 **Pegado Rápido de Guion:**
  Haz **clic derecho** sobre la isla para reemplazar el guion inmediatamente con el texto de tu portapapeles (`CF_UNICODETEXT`).
- 🪶 **Optimización de Área Física (Zero Click Blocking):**
  Cuando la isla está contraída en reposo, la ventana física de Windows se reduce a tan solo `220 × 62 px`. No bloquea la selección de texto ni los clics en la mitad superior de la pantalla.
- 🎛️ **Configuración Nativa en Windhawk:**
  Ajusta el guion predeterminado, velocidad inicial, tamaño de fuente, nivel de opacidad (transparencia) y margen superior directamente en la interfaz de Windhawk.

---

## ⌨️ Controles y Accesos Rápidos

| Atajo | Acción | Descripción |
| :--- | :--- | :--- |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Espacio</kbd> | **Pausar / Reanudar** | Detiene o continúa el desplazamiento del guion. |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>R</kbd> | **Reiniciar Texto** | Vuelve el guion al inicio y lo pone en pausa. |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd> | **Expandir / Contraer** | Abre o cierra manualmente la isla de teleprónter. |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>G</kbd> | **Modo Fantasma** | Conmuta el paso de clics a través de la ventana. |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>X</kbd> | **Panel de Atajos** | Despliega o guarda el cajón interactivo de atajos. |
| **Doble Clic Rápido** ($\le 300\text{ ms}$) | **Reiniciar Texto** | Regresa el texto al principio de inmediato. |
| **Clic Simple** | **Pausar / Reanudar** | Alterna la reproducción del texto. |
| **Rueda del Ratón** | **Ajustar Velocidad** | Aumenta o disminuye la velocidad en $\pm 5\text{ px/s}$. |
| **Clic Derecho** | **Pegar Portapapeles** | Carga el texto copiado en el teleprónter. |
| **Botón Amarillo (🟡 👻)** | **Activar Fantasma** | Botón circular superior derecho para entrar al modo fantasma. |

---

## 🛠️ Instalación en Windhawk

1. Instala **[Windhawk](https://windhawk.net/)** en tu equipo (Windows 10 o Windows 11).
2. Abre la ventana principal de Windhawk y dirígete a la pestaña **Mods** > **Mod Manager**.
3. Haz clic en los tres puntos (`...`) en la esquina superior derecha y selecciona **New Mod** (Nuevo Mod).
4. Asigna un identificador (ejemplo: `dynamic-island-teleprompter`).
5. Copia el código fuente completo del archivo [`dynamic-island-teleprompter.wh.cpp`](dynamic-island-teleprompter.wh.cpp) y pégalo en el editor de Windhawk.
6. Haz clic en **Save and Compile** (Guardar y Compilar).
7. ¡Listo! La isla aparecerá centrada en el borde superior de tu pantalla.

---

## ⚙️ Parámetros de Configuración (`@WindhawkModSettings`)

Puedes personalizar el comportamiento desde la pestaña **Details** / **Settings** del mod en Windhawk:

- **Guion de lectura (`script_text`):** El texto que se mostrará y desplazará por defecto en el teleprónter.
- **Velocidad de lectura (`default_speed`):** Velocidad inicial en píxeles por segundo (por defecto: `35 px/s`).
- **Tamaño de fuente (`font_size`):** Tamaño en puntos de la tipografía (por defecto: `21 pt`, usa *Segoe UI Variable Display*).
- **Opacidad de la isla (`island_opacity`):** Nivel de transparencia de la cápsula (10% a 100%, por defecto: `92%`).
- **Distancia superior (`top_margin`):** Distancia en píxeles desde el marco superior (por defecto: `12 px`).

---

## 🔨 Compilación Manual desde Consola

Si deseas compilar la biblioteca directamente usando el compilador de Windhawk:

```powershell
& "C:\Program Files\Windhawk\Compiler\bin\clang++.exe" `
    -shared -O2 -std=c++23 `
    -I"C:\Program Files\Windhawk\Compiler\include" `
    -include "windhawk_api.h" `
    dynamic-island-teleprompter.wh.cpp `
    -o dynamic-island-teleprompter.dll `
    -ld2d1 -ldwrite -lole32 -lshcore -ldwmapi
```

---

## 📜 Licencia y Créditos

- **Autor:** [0xCh4inz](https://github.com/0xCh4inz)
- **Licencia:** Distribuido bajo la Licencia [MIT](LICENSE).
- **Agradecimientos:** Inspirado en la arquitectura visual de [devcode90/Dynamic-Island-for-Windows](https://github.com/devcode90/Dynamic-Island-for-Windows).
