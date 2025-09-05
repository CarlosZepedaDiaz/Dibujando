# 🎨 Laboratorio de Dibujo Libre

## Descripción del Proyecto

Este laboratorio de programación presenta una aplicación web interactiva desarrollada en React que permite a los usuarios dibujar libremente en un canvas digital con múltiples opciones de color. La aplicación está optimizada para proporcionar una experiencia de dibujo fluida y creativa.

## 🎯 Objetivos de Aprendizaje

Al completar este laboratorio, los estudiantes habrán:

1. **Trabajado con Canvas HTML5**: Manipulación directa del elemento canvas para crear aplicaciones de dibujo
2. **Implementado Event Handling**: Manejo de eventos de mouse, touch y pointer para dispositivos múltiples
3. **Aplicado React Hooks**: Uso avanzado de useState, useRef, useEffect y useCallback
4. **Desarrollado Interfaces Interactivas**: Creación de selectores de color y controles de usuario
5. **Optimizado Performance**: Técnicas de optimización para aplicaciones interactivas en tiempo real
6. **Implementado Responsive Design**: Diseño adaptable para diferentes dispositivos

## 🛠️ Tecnologías Utilizadas

- **React 18**: Framework principal para la interfaz de usuario
- **Vite**: Herramienta de build y desarrollo rápido
- **HTML5 Canvas**: Para el área de dibujo interactiva
- **CSS3**: Estilos modernos con gradientes y animaciones
- **JavaScript ES6+**: Programación moderna con módulos y funciones avanzadas

## 📋 Funcionalidades Implementadas

### ✅ Funcionalidades Implementadas
- Canvas de dibujo responsivo (800x600px)
- Soporte para mouse, lápiz óptico y touch (dispositivos móviles)
- Selector de color con opciones predefinidas:
  - 🔴 Rojo
  - 🔵 Azul
  - 🟢 Verde
  - 🟡 Amarillo
  - 🟣 Morado
  - 🟠 Naranja
  - ⚫ Negro
  - ⚪ Blanco
- Selector de color personalizado (color picker)
- Botón para limpiar el canvas
- Interfaz de usuario intuitiva y moderna

## 🏗️ Arquitectura del Proyecto

```
react-drawing-lab/
├── public/
│   └── vite.svg
├── src/
│   ├── components/
│   │   ├── DrawingCanvas.jsx    # Componente principal del canvas
│   │   └── DrawingCanvas.css    # Estilos del canvas
│   ├── App.jsx                  # Componente raíz de la aplicación
│   ├── App.css                  # Estilos principales
│   ├── index.css                # Estilos globales
│   └── main.js                  # Punto de entrada de React
├── index.html                   # Archivo HTML principal
├── package.json                 # Dependencias y scripts
├── vite.config.js              # Configuración de Vite
└── LABORATORIO.md              # Esta documentación
```

## 🔧 Instalación y Ejecución

### Prerrequisitos
- Node.js (versión 16 o superior)
- npm o yarn

### Pasos de Instalación

1. **Clonar o descargar el proyecto**
   ```bash
   # Si tienes el proyecto en un repositorio
   git clone [URL_DEL_REPOSITORIO]
   cd react-drawing-lab
   ```

2. **Instalar dependencias**
   ```bash
   npm install
   ```

3. **Ejecutar en modo desarrollo**
   ```bash
   npm run dev
   ```

4. **Abrir en el navegador**
   - Navegar a `http://localhost:5173/`
   - La aplicación se recargará automáticamente al hacer cambios

5. **Construir para producción**
   ```bash
   npm run build
   ```

## 🧠 Conceptos Técnicos Clave

### 1. Manejo del Canvas HTML5

```javascript
// Configuración inicial del canvas
const canvas = canvasRef.current;
const ctx = canvas.getContext('2d');
ctx.lineCap = 'round';
ctx.lineJoin = 'round';
ctx.lineWidth = 3;
```

### 2. Event Handling Multi-dispositivo

```javascript
// Soporte para mouse y touch
const getPosition = (e) => {
  if (e.touches && e.touches[0]) {
    // Touch event
    return { x: e.touches[0].clientX, y: e.touches[0].clientY };
  } else {
    // Mouse event
    return { x: e.clientX, y: e.clientY };
  }
};
```

### 3. Algoritmos de Detección de Formas con IA

```javascript
// Extracción de características avanzadas
const features = extractAdvancedFeatures(stroke);
const prediction = await classifyWithNeuralNetwork(features);

// Detección con TensorFlow.js
if (prediction.circle > 0.7) {
  return '🔵 Círculo';
} else if (prediction.square > 0.7) {
  return '🟦 Cuadrado';
} else if (prediction.triangle > 0.7) {
  return '🔺 Triángulo';
}
```

### 4. Optimización con React Hooks

```javascript
// useCallback para optimizar renders
const startDrawing = useCallback((e) => {
  // Lógica de inicio de dibujo
}, [dependencies]);
```

## 🎓 Ejercicios Propuestos

### Nivel Básico
1. **Modificar colores**: Cambiar el color del trazo dinámicamente
2. **Ajustar grosor**: Implementar control de grosor de línea
3. **Mejorar precisión**: Ajustar umbrales de confianza para las 3 formas

### Nivel Intermedio
4. **Múltiples colores**: Permitir selección de color antes de dibujar
5. **Historial de trazos**: Implementar funcionalidad de deshacer/rehacer
6. **Exportar imagen**: Añadir botón para descargar el dibujo como PNG
7. **Métricas de confianza**: Mostrar porcentaje de confianza de la predicción

### Nivel Avanzado
8. **Optimizar modelo**: Mejorar la arquitectura de la red neuronal
9. **Colaboración en tiempo real**: Usar WebSockets para dibujo colaborativo
10. **Nuevas formas**: Entrenar el modelo para detectar pentágonos y hexágonos

## 🐛 Debugging y Troubleshooting

### Problemas Comunes

1. **Canvas no responde en móviles**
   - Verificar que `touch-action: none` esté aplicado
   - Asegurar que los eventos touch estén manejados correctamente

2. **Detección imprecisa**
   - Ajustar los umbrales en las funciones de detección
   - Mejorar el algoritmo de análisis de formas

3. **Performance lenta**
   - Optimizar la frecuencia de detección
   - Usar `requestAnimationFrame` para animaciones suaves

## 📚 Recursos Adicionales

- [MDN Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [React Hooks Documentation](https://reactjs.org/docs/hooks-intro.html)
- [Vite Documentation](https://vitejs.dev/)
- [HTML5 Touch Events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events)

## 🏆 Criterios de Evaluación

| Criterio | Peso | Descripción |
|----------|------|-------------|
| **Funcionalidad** | 40% | La aplicación funciona correctamente y detecta formas |
| **Código Limpio** | 25% | Código bien estructurado y comentado |
| **UI/UX** | 20% | Interfaz intuitiva y responsive |
| **Innovación** | 15% | Funcionalidades adicionales implementadas |

## 👥 Créditos

Este laboratorio fue diseñado para el curso de **Programación Avanzada** como una introducción práctica a:
- Desarrollo web moderno con React
- Manipulación de Canvas HTML5
- Algoritmos de reconocimiento de patrones
- Optimización de aplicaciones interactivas

---

**¡Feliz coding! 🚀**

*Recuerda: La programación es un arte, y cada línea de código es un trazo en tu lienzo digital.*