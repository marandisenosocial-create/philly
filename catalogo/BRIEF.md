# MARAN × LayerSon Creative House — Dirección del catálogo web

Documento de dirección. Es la fuente de verdad del proyecto: si algo cambia, se cambia aquí primero.
Última revisión: 6 de septiembre de 2026.

## 1. Qué es

Una casa donde una idea pasa de diseño a objeto. Dos manos, una sola cara al cliente.

- **Maran** hace lo que se ve y se vive: momentos de vida (boda, cumpleaños, baby shower, nacimiento, pedida de mano, bridal shower, bautizo, XV años) vendidos como experiencia completa, y colecciones de temporada (Halloween, Navidad, San Valentín).
- **LayerSon** hace lo que se usa y se queda: merch por volumen (uniformes, playeras, llaveros, totebags, termos, displays con NFC, corte láser) y piezas a la medida (industrial, colección, refacción). También tiene temporadas (por ejemplo, termos en temporada de futbol).
- **La Casa** es literal: una casa antigua junto a la de Magda y Adán, en adaptación, donde se diseña y se fabrica. Es el relato del sitio.

Concepto: **"Diseñamos ideas. Fabricamos posibilidades."**
Línea de apoyo: "Desde la invitación hasta el último recuerdito. Y si algo no existe, lo fabricamos."

## 2. Decisiones tomadas (no reabrir sin motivo)

1. **El cliente nunca elige marca. Elige momento.** Las marcas aparecen como créditos ("Diseño: Maran · Fabricación: LayerSon"), no como puertas.
2. **Maran vende paquetes, no piezas.** Cada experiencia tiene alcance fijo (qué incluye, cantidades base, qué mueve el precio). El precio "desde" va en el paquete.
3. **Maran no vende a negocios.** Nada de "vestimos tu negocio", menús o etiquetas recurrentes como servicio. La barra de café es una relación especial, no una oferta.
4. **Para negocios solo se vende lo que LayerSon fabrica:** uniformes, merch promocional, displays con NFC, corte láser, piezas a la medida.
5. **La barra de café aparece solo dentro de Experiencias**, como "barra de café para tu evento", sin nombre del negocio ni palabra "cliente".
6. **Todo lo que se muestra se puede pedir tal cual.** Si algo sale en una foto y no se vende, se recorta.
7. **Coordinación de eventos sí se ofrece** (ya hay dos casos reales), como "Eventos completos".
8. **Temporadas abren con cupo y fecha de cierre.** El sitio muestra "cerrada" sin borrar nada.
9. **Sin carrito.** Contacto por WhatsApp con mensaje prellenado.
10. **Personajes con licencia (Disney, NFL, etc.) no se exhiben en el sitio.** Producir por encargo es una cosa; publicarlo como portafolio comercial es exposición legal. Se muestran piezas sin personaje visible o en colores de equipo sin logos.

## 3. Arquitectura

| Sección | Marca | Cómo se compra |
|---|---|---|
| Momentos | Maran | Paquete por evento. Precio "desde" por nivel |
| Temporada | Maran y LayerSon | Colección con precio fijo, fecha de cierre y cupo |
| Para tu negocio | LayerSon | Producto por lote: "desde $ por X piezas" |
| A la medida | LayerSon | Foto + descripción + cantidad. Sin precio, con casos |
| La Casa | Ambas | Relato, no venta |

Momentos principales (los más pedidos hoy): **Boda, Cumpleaños, Baby shower, Nacimiento.**
Otros momentos (visibles, sin paquete todavía): Pedida de mano, Bridal shower, Bautizo, XV años.

Cada experiencia se presenta como línea de tiempo del evento: **antes / durante / después.**

## 4. Dirección visual

Base tomada de los renders de la Casa (confirmados por Magda como "así será"):

- **Maran:** hueso cálido, madera clara, luz natural, serif con carácter.
- **LayerSon:** carbón, azul eléctrico (LED), madera oscura, hexágono con cactus, sans geométrica.

En el sitio: la página vive en el terreno de Maran (hueso) y las secciones de LayerSon cambian a carbón con azul como acento. Dos cuartos de una misma casa.

Tipografía: Fraunces (display Maran), Anton (display LayerSon, solo en títulos grandes), Plus Jakarta Sans (texto). Coherente con el sistema interno de Philly.

Evitar: iconos decorativos, degradados, más de un acento por cuarto, bloques de texto largos, apariencia infantil, apariencia de tienda.

Fotografía: producto real, fondo limpio, la pieza sola y luego el conjunto en mesa, luz de día, sin gente de fondo. Los renders de la Casa se muestran como "así será", nunca como "nuestro taller".

## 5. Modelo de datos del catálogo (v0)

Los datos viven en el bloque `CATALOGO` al inicio de `index.html`. Cuando crezca, se mueven a un Google Sheet o JSON.

- `config`: whatsapp, instagram (vacíos hasta que Magda los confirme).
- `momentos[]`: id, nombre, frase, antes[], durante[], despues[], desde (número o null).
- `otrosMomentos[]`: nombre.
- `temporadas[]`: id, nombre, marca, descripcion, abre (fecha o null), cierra (fecha o null), desde. Estado calculado: próximamente / abierta / cerrada.
- `negocio[]`: nombre, descripcion, lote, desde.
- `aMedida[]`: titulo, descripcion.

Regla: **nunca inventar precios.** `desde: null` muestra "a cotizar".

## 6. Pendientes que sí cambian decisiones

- [ ] Número de WhatsApp e Instagram oficiales.
- [ ] Logos de Maran y LayerSon en vector o PNG grande.
- [ ] Un paquete real ya cobrado (qué incluía y cuánto) para calibrar el primer "desde".
- [ ] Tres o cuatro productos de LayerSon por lote con precio real.
- [ ] Fotos de los dos eventos coordinados y del evento Tres Marías (solo piezas sin personaje).
- [ ] Confirmar las listas antes/durante/después de cada momento (son propuesta a partir de lo que Magda ha mencionado).
- [ ] Repositorio propio para el catálogo. Hoy vive en `philly/catalogo/` de forma temporal.

## 7. Contenido que ya existe

- Renders de la Casa: `img/casa-maran.jpg`, `img/casa-layerson.jpg`.
- Caso Tres Marías (cumpleaños, tema congelado): menú de cafecito frío, recuerditos con crayolas y plastilina, vasos con topper de copo, hojas de actividades. Solo se puede publicar lo que no muestre personajes.
- Caso barra de café: barra en melamina (corte láser), uniformes, menús. Se usa recortado dentro de Experiencias.
