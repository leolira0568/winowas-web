# WinOWAS Web

Versión web, libre y de código abierto, de **WinOWAS**: la herramienta para analizar posturas de trabajo con el método **OWAS** (*Ovako Working posture Analysing System*).

El WinOWAS original era un programa de Windows 3.x de 16 bits (Visual Basic 3) que deja de funcionar a partir de Windows de 64 bits. Este proyecto lo reemplaza con **un solo archivo HTML**:

- Funciona sin instalación ni conexión a internet: se abre con doble clic en cualquier navegador moderno.
- Abre y guarda archivos **`.OWS` compatibles con el WinOWAS original**, así que los estudios existentes siguen sirviendo.
- Funciona en Windows, macOS, Linux, tabletas y celulares.

**▶ Usar en línea:** https://leolira0568.github.io/winowas-web/

## Funciones

- **Datos generales**: empresa, departamento, trabajo estudiado, observador, fecha, hora, intervalo de observación y fases de trabajo.
- **Observar**: reloj con aviso sonoro en cada intervalo, selección de postura con botones grandes o con el teclado (`2341` + Enter) y categoría de acción al instante. Se puede repetir la anterior y deshacer la última.
- **Categorías de acción**: distribución en las categorías 1–4 con sus recomendaciones, desglose por fase de trabajo y posturas agrupadas por categoría.
- **Por parte del cuerpo**: porcentaje del tiempo en cada postura de espalda, brazos y piernas, comparado con los límites de cada categoría.
- **Archivos**: abrir, guardar, guardar como y unir archivos `.OWS`.
- **Imprimir o guardar en PDF**, y copiar los resultados al portapapeles (se pegan como tabla en Excel o Word).
- **Autoguardado** en el navegador para no perder trabajo.

## Cómo usarlo sin internet

1. Descarga [`WinOWAS.html`](WinOWAS.html) (botón *Download raw file* en GitHub).
2. Ábrelo con doble clic. Con Edge o Chrome, *Guardar* sobrescribe directamente el archivo `.OWS` abierto. En otros navegadores, el archivo se descarga.

En la carpeta [`ejemplos/`](ejemplos/) hay un estudio de muestra para probar.

## Método OWAS

Cada observación se codifica con cuatro dígitos:

| Dígito | Parte | Códigos |
|---|---|---|
| 1 | Espalda | 1 recta · 2 inclinada · 3 girada · 4 inclinada y girada |
| 2 | Brazos | 1 ambos bajo el hombro · 2 uno sobre el hombro · 3 ambos sobre el hombro |
| 3 | Piernas | 1 sentado · 2 de pie, piernas rectas · 3 de pie, una pierna recta · 4 de pie, rodillas flexionadas · 5 de pie, una rodilla flexionada · 6 arrodillado · 7 caminando |
| 4 | Carga | 1 < 10 kg · 2 10–20 kg · 3 > 20 kg |

| Categoría | Significado |
|---|---|
| 1 | Postura normal. No se requieren acciones. |
| 2 | Se requieren acciones correctivas en un futuro cercano. |
| 3 | Se requieren acciones correctivas lo antes posible. |
| 4 | Se requieren acciones correctivas inmediatamente. |

## Formato de archivo `.OWS`

Texto plano con codificación Windows-1252 y finales de línea CRLF:

```
!OWAS!
"Empresa"
"Departamento"
"Trabajo estudiado"
"Observador"
"dd/mm/aaaa"
"hh:mm"
 N                ← número de fases (con un espacio antes y otro después)
"Fase 1"          ← N nombres de fase
...
30                ← intervalo en segundos
M                 ← número de observaciones
23330             ← M códigos: espalda, brazos, piernas, carga e índice de fase (desde 0)
...
```

## Aviso

Este proyecto es una reimplementación independiente. No está afiliado a la Universidad Tecnológica de Tampere ni a los autores del WinOWAS original, y no incluye ninguna parte de su programa. Las tablas de clasificación corresponden al método OWAS publicado, tal como las usaba el WinOWAS original.

Los resultados son una ayuda para la evaluación ergonómica y no sustituyen el criterio de un profesional.

## Licencia

[MIT](LICENSE) © 2026 Leonardo

Los iconos de la interfaz están basados en [Lucide](https://lucide.dev) (licencia ISC, © Lucide Contributors). Los pictogramas de postura son propios del proyecto.
