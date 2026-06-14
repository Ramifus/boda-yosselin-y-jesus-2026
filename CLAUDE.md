# Proyecto: Invitación Digital de Boda — Juan Iris & Jhonathan

## Stack
- **Framework:** Astro
- **Estilos:** Tailwind CSS
- **Animaciones:** GSAP + ScrollTrigger (NO usar AOS)
- **Fuentes:**
  - `font-great-vibes` → títulos elegantes/cursivos (ej. "Nuestros Padres", "Itinerario")
  - `font-crimson` → textos generales
  - `font-cormorant-sc` → textos de nombres/contenido (requiere `<style>` local con `font-family: "Cormorant SC", serif`)
  - `font-charm` → números grandes
- **Color principal:** `#122a4d` (azul oscuro)
- **Color dorado:** `#c9a961`

---

## Datos de los Novios (de información.txt)

| Campo | Valor |
|---|---|
| Novia | Juana Iris |
| Novio | Jhonathan |
| Fecha | Sábado 20 de junio de 2026 |
| WhatsApp Novia | +591 77338445 |
| WhatsApp Novio | +591 75657551 |

### Padres
- **Novia:** Delmira Tacoo Pei / Juan de Dios Arancibia Campos
- **Novio:** Gladys Orellana Calderón / Mariano Garrado Mendoza

### Padrinos de Religión
- Kattia Gabriela Molina Galvarro
- Wilson Augusto Domínguez Pradel

### Testigos
- María Brenda Guzmán Castro
- Alejandra Isabel García Hoyos

### Ceremonia Religiosa
- **Iglesia:** Catedral de San Miguel de Velasco
- **Hora:** 16:00
- **Mapa:** https://maps.app.goo.gl/KJ9sq4knmzq6ib8A8

### Recepción Social
- **Lugar:** Convento Santa Miguel (Hnas. Terciarias Franciscanas)
- **Hora:** 19:30
- **Mapa:** https://maps.app.goo.gl/iVE6zLrURo3yy7Qt5

### Itinerario
- Ceremonia Religiosa: 16:00 Hrs.
- Ceremonia Civil y Recepción: 17:00 Hrs.
- Brindis: 17:30 Hrs.
- Cena: 19:30 Hrs.
- Fiesta y Baile: 20:30 Hrs.

### Código de Vestimenta
- **Caballeros:** Traje Formal — NO ASISTIR DE COLOR AZUL O BEIGE
- **Damas:** Vestido Largo — NO ASISTIR DE COLOR BLANCO

### Confirmación de Asistencia (WhatsApp)
- Texto: `"Me complace confirmar mi asistencia a la boda de Jhonathan y Juana Iris. Nos vemos el sábado 20 de junio. ¡Estaré sin falta!"`
- Novia: `https://wa.me/59177338445?text=...`
- Novio: `https://wa.me/59175657551?text=...`

---

## Estructura de Componentes (orden en index.astro)

```
Portada
NombresFlores      ← tarjetas con fecha (día 20, Juana Iris & Jhonathan)
Cita               ← Eclesiastés 4:12
Contador           ← fecha 20/06/2026 a las 16:00
Calendario         ← día especial = 20, mes = 6
DireccionCeremonia ← Catedral San Miguel, 16:00
DireccionRecepcion ← Convento Santa Miguel, 19:30
NombresPadres
Padrinos           ← incluye sección Testigos
Fotos3             ← foto principal con marco dorado elegante
Itinerario
CodigoVestimenta
Aclaracion         ← NUEVO: niños en iglesia OK, cena solo adultos
Compartirfotos     ← botones WhatsApp novia y novio
Confirmar          ← botones WhatsApp para confirmar asistencia
Despedida
```

---

## Cambios Realizados en Esta Sesión

### Portada.astro
- Nombres: `Fabiana & Yamil` → `Juana Iris & Jhonathan`

### NombresFlores.astro
- Día: `13` → `20`
- Nombres tarjeta: `Fabiana & Yamil` → `Juana Iris & Jhonathan`

### NombresPadres.astro
- Datos de padres actualizados
- `rounded-lg` → `rounded-2xl` (esquinas iguales a Dirección)

### Padrinos.astro
- Nombres de padrinos actualizados
- Añadida sección **Testigos**
- `rounded-lg` → `rounded-2xl`

### Contador.astro
- Día `13` → `20`, Hora `15` → `16`

### Calendario.astro
- `DIA_ESPECIAL = 13` → `20`

### DireccionCeremonia.astro
- Iglesia, hora y mapa actualizados
- Eliminada dirección secundaria (solo nombre de iglesia)

### DireccionRecepcion.astro
- Lugar, hora y mapa actualizados
- Eliminada dirección secundaria

### Itinerario.astro
- Hora ceremonia: `15:00` → `16:00 Hrs.`
- Todas las horas tienen sufijo `Hrs.` y tamaño `text-lg`
- Título cambiado a `font-great-vibes`

### CodigoVestimenta.astro
- Texto visible por sección: Traje Formal / NO COLOR AZUL O BEIGE (Caballeros); Vestido Largo / NO COLOR BLANCO (Damas)
- Texto de restricción: `text-base`
- Título estilo `font-great-vibes`: "Dress Code"

### Confirmar.astro
- Reemplazado Google Forms por 2 botones WhatsApp (Novia y Novio) con texto predeterminado

### Compartirfotos.astro
- Reemplazado botón Google Photos por 2 botones WhatsApp (Novia y Novio) para enviar fotos

### Fotos3.astro
- Rediseñado completamente: marco dorado con esquinas decorativas, título "Nosotros", animaciones GSAP elegantes, modal oscuro con blur
- Foto muestra tamaño original (sin `object-cover`)
- Eliminados nombres del pie de foto y modal

### Aclaracion.astro ← NUEVO COMPONENTE
- Estilo igual a Itinerario (card con `fondoplomo.png`, botón decorativo, bordes redondeados)
- Título con `font-great-vibes`
- Texto con `font-cormorant-sc text-lg`
- Contenido: iglesia con niños OK, cena solo adultos
- Ubicado después de CodigoVestimenta en index.astro

### Despedida.astro
- 4 párrafos con nuevo mensaje personalizado
- Final: "Con amor, / ¡Los esperamos!" en `font-great-vibes`

---

## Convenciones del Proyecto

- **Botón decorativo superior** en todas las cards: `boton.png` a `top: -30px`
- **Fondos de cards claras:** `fondoplomo.png`
- **Fondos de cards oscuras/rojas:** `fondorojo.png` o `azul.png`
- **Esquinas redondeadas cards:** `rounded-2xl` (dirección/padres/padrinos) o `rounded-[40px]` (itinerario/confirmar/vestimenta)
- **IDs únicos** por componente para evitar conflictos GSAP
- **ScrollTrigger:** `start: "top 80%"`, `toggleActions: "play none none reset"`
- **Fuente cormorant-sc** siempre necesita bloque `<style>` local definiendo `font-family`
- **Links WhatsApp Bolivia:** formato `https://wa.me/591XXXXXXXX`
