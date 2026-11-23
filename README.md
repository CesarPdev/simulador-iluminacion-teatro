# 🎭 Simulador de Consola de Iluminación Teatral (LUMEN-3000)

Simulador interactivo de consola de iluminación escénica diseñado para ensayar y visualizar transiciones de luces cenitales y marcaciones de actores en tiempo real sobre un escenario teatral dividido en 3 canales y zonas dramáticas.

Desarrollado en una **arquitectura en un solo archivo independiente** (`index.html`) con HTML5, CSS3 moderno y Vanilla JavaScript, sin dependencias externas obligatorias ni pasos de compilación.

---

## 🚀 Cómo Ejecutar

Puedes abrir el simulador de cualquiera de las siguientes formas:

1. **Directo en el navegador:**  
   Haz doble clic sobre el archivo [`index.html`](file:///home/cesar/Documentos/Mi%20radio%20magica/index.html) o arrástralo a Google Chrome, Firefox, Safari o Edge.

2. **Servidor local rápido (Python):**
   ```bash
   python3 -m http.server 8000
   ```
   Y abre `http://localhost:8000` en tu navegador.

---

## 🌟 Características Principales

### 1. Escenario Teatral Inmersivo (`100vh` x `100vw`, Sin Scroll)
- **Estética oscura y teatral:** Ciclorama con textura aterciopelada y sombras sutiles de telón, vara superior de tramoya (*truss/catwalk*) y piso de escenario en perspectiva 3D con tablones de madera oscuros.
- **División en 3 Zonas Iguales:**
  - **Canal 1:** Zona Izquierda (*Habitación y Familia*)
  - **Canal 2:** Zona Centro (*Presentador*)
  - **Canal 3:** Zona Derecha (*Mesa con 4 Comensales*)
  - Líneas divisorias lumínicas discretas y marcas de cinta de posición (*spike marks*) en el suelo para cada actor.
- **Reflectores Cenitales de Alta Fidelidad:**
  - Focos con viseras cortadoras (*snout/barndoors*), aletas de refrigeración y lente de Fresnel con anillo concéntrico y halo de incandescencia.

### 2. Escenografía y Personajes Reactivos a la Iluminación
- **Iluminación Asimétrica Reactiva:**
  - Cuando una luz cenital está apagada, la escenografía y los personajes permanecen en **penumbra teatral profunda** (siluetas oscuras, `brightness(0.12)`).
  - Al encender la luz (`.is-on`), se iluminan cálidamente en sincronía con el **Fade In de 500ms** (`0.5s ease-out`).
  - Al apagar la luz, regresan suavemente a la oscuridad con el **Fade Out de 1000ms** (`1.0s ease-in-out`), sin desaparecer de escena.
- **Zona 1 (Izquierda):**
  - **Escenografía fija:** Cama victoriana en madera noble con edredón y almohadas.
  - **Personajes interactivos:**
    - **Abuelo:** Conmutable con la tecla **`A`**.
    - **Hija:** Conmutable con la tecla **`H`**.
    - **Nieta:** Conmutable con la tecla **`N`**.
- **Zona 2 (Centro):**
  - **Presentador:** Ubicado de pie sobre el *spike mark* con traje de etiqueta, micrófono y carpeta de notas. Conmutable con la tecla **`P`**.
- **Zona 3 (Derecha):**
  - **Mesa con 4 Comensales (Fija):** Mesa de banquete en perspectiva con 4 comensales conversando (dos laterales en perfil 3/4 y dos al fondo mirando directamente al público, sin dar la espalda a la audiencia).

### 3. Tiempos de Transición (Estrictamente Calibrados)
- **Fade In (Encendido):** `500 ms` (`0.5s ease-out`).
- **Fade Out (Apagado):** `1000 ms / 1 segundo` (`1.0s ease-in-out`).
- **Entradas / Salidas de Elenco:** `350 ms` (`0.35s ease`) con fade de opacidad y desplazamiento sutil.

### 4. Consola HUD Flotante y Controles
- **Barra de Control Discreta:**
  - Indicadores en tiempo real para **CH 1**, **CH 2** y **CH 3** con LEDs de estado (verde = ON, gris = OFF).
  - Mini-barra de control de elenco con botones píldora (*cast pills*) interactivos.
  - Botón **Blackout** con acento carmesí que ejecuta un fade out general simultáneo de 1.0s.
  - Botón **Full On** con acento dorado que ejecuta un fade in general simultáneo de 500ms.
  - Botón **Vaciar Escenario** con acento lavanda para retirar de inmediato a todo el elenco (tecla `V`).
  - Selector de **Filtros de Gel Teatral** (Cálido 3200K, Luz Día 4000K, Ámbar #02, Azul Escena #68).
  - Efectos de sonido de **relé electromecánico** y **pasos escénicos** generados vía *Web Audio API*.

---

## ⌨️ Atajos de Teclado

| Tecla / Acción | Función |
| :--- | :--- |
| **`1`** (o Numpad 1) / Clic en Columna 1 | Alternar Luz Canal 1 (Izquierda) — *In 0.5s / Out 1s* |
| **`2`** (o Numpad 2) / Clic en Columna 2 | Alternar Luz Canal 2 (Centro) — *In 0.5s / Out 1s* |
| **`3`** (o Numpad 3) / Clic en Columna 3 | Alternar Luz Canal 3 (Derecha) — *In 0.5s / Out 1s* |
| **`Espacio`**, **`0`**, o **`B`** | **Blackout General** (Fade Out de 1.0s) |
| **`F`** | **Full On General** (Fade In de 0.5s) |
| **`V`** | **Vaciar Escenario** (Retira todos los personajes activos) |
| **`A`** | Entrada / Salida: **Abuelo** (Zona 1) |
| **`H`** | Entrada / Salida: **Hija** (Zona 1) |
| **`N`** | Entrada / Salida: **Nieta** (Zona 1) |
| **`P`** | Entrada / Salida: **Presentador** (Zona 2) |
| **`Esc`** | Abrir/Cerrar panel de atajos y ayuda |
