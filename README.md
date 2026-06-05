# 🌀 ECOS

> Coordínate con tus yos del pasado.

Un puzzle web sobre el **tiempo**: cuando te atascas, creas un **eco** que repite tus movimientos anteriores. Así un "tú" del pasado mantiene un botón pisado mientras el "tú" del presente cruza la puerta.

**▶ Jugar:** abre `index.html` en cualquier navegador (o publícalo con GitHub Pages).

## Características

- 🌐 **Bilingüe (ES / EN)** con detección automática del idioma del navegador y selector en Ajustes.
- 🧩 **155 niveles** con dificultad creciente, en 6 mundos (Tutorial → Leyenda) + un mundo bonus de **📦 Cajas**.
- 🔗 **Mecánica de cadenas:** en los mundos avanzados cada botón se esconde tras la puerta que abre el anterior.
- 📦 **Cajas empujables:** colócalas sobre los botones para mantener puertas abiertas sin gastar un eco.
- 🎨 **Botones y puertas con color + símbolo** (accesible para daltónicos).
- 🛠️ **Editor de niveles** con códigos para compartir tus creaciones.
- 📅 **Reto del día** + 🔥 racha diaria + 🏆 logros + ⭐ estrellas como llave.
- 📲 **PWA:** instalable en el móvil y jugable **sin conexión**.
- ⚙️ **Ajustes:** sonido, música, vibración, animaciones y reinicio de progreso.
- 📱🖥️ Responsive: se juega bien en móvil (táctil) y en PC (teclado).
- 🎉 Confetti, vibración y sonido. Cero dependencias.

## Controles

| Acción | Teclado | Móvil |
|---|---|---|
| Mover | Flechas / WASD | Pad o deslizar |
| Esperar un turno | Espacio | Botón ⏸ |
| Crear eco | Enter / E | Botón ⟲ |
| Deshacer | Z | Botón ↶ |
| Reiniciar | R | Botón ⟳ |

## Cómo se juega

1. Llega al **portal verde** 🟢.
2. Los **botones** abren la **puerta del mismo color/símbolo**… pero solo mientras alguien los pisa.
3. Crea un **eco** ⟲: vuelves al inicio y tu recorrido anterior se repite como un fantasma. Deja que el eco pise el botón mientras tú cruzas.
4. Usa **esperar** ⏸ para sincronizarte con tus ecos.

## 💰 Monetización (adaptada al destino con un solo `CONFIG`)

Toda la configuración está en **un único bloque `CONFIG`** al principio del `<script>` de `index.html`. El mismo archivo sirve para tu web **y** para los portales: el campo `BUILD` decide qué publicidad usa.

```js
const CONFIG = {
  BUILD:               "auto", // "auto" | "self" | "poki" | "crazygames"
  ADSENSE_CLIENT:      "",      // "ca-pub-XXXXXXXXXXXXXXXX"  (solo build self)
  STRIPE_PAYMENT_LINK: "",      // "https://buy.stripe.com/xxxxxxxx" (solo build self)
  GAME_URL:            "https://cristiiaanlp.github.io/ecos/"
};
```

### 🎯 Builds (mejora "separar versión propia / portal")
`BUILD: "auto"` **detecta el portal por el dominio** donde se sirve el juego, así que **no tienes que tocar nada**:

| Build | Dónde | Publicidad | AdSense/Stripe |
|---|---|---|---|
| **self** | tu web (GitHub Pages, dominio propio) | AdSense H5 + "quitar anuncios" con Stripe | ✅ activos |
| **poki** | servido desde `*poki*` | **Poki SDK** (anuncios del portal) | ❌ desactivados |
| **crazygames** | servido desde `*crazygames*` | **CrazyGames SDK** (anuncios del portal) | ❌ desactivados |

- Los portales **no permiten publicidad/pagos propios**: en sus builds se ocultan AdSense, Stripe y la opción "quitar anuncios", y se cargan **su SDK** + las señales `gameplayStart` / `gameplayStop` y los intersticiales/recompensados nativos.
- Si el SDK del portal no carga (p. ej. en local), el juego sigue funcionando en modo **simulado**.
- ¿Quieres forzar un build para probar en local? Cambia `BUILD` a `"poki"` o `"crazygames"`.

**Build "self" — Anuncios (AdSense for Games / H5):** pista recompensada (💡) + intersticial cada 3 niveles.
- Crea cuenta en **Google AdSense**, activa **H5 Games Ads** y pega tu ID en `ADSENSE_CLIENT`.
- Sube el juego a tu dominio **https** y espera la aprobación.

**Build "self" — Quitar anuncios (1,99 €) con Stripe:** sin servidor, usando un **Payment Link**.
- En Stripe → **Payment Links**, crea un enlace de 1,99 € que tras el pago redirija a `GAME_URL?paid=1`.
- Pega ese enlace en `STRIPE_PAYMENT_LINK`.
- ⚠️ Es un desbloqueo del lado cliente (suficiente para un extra de 1,99 €). Para verificación 100% fiable haría falta un backend con webhook de Stripe.

**Builds de portal — no necesitas credenciales:** sube el `index.html` tal cual a Poki / CrazyGames; ellos lo sirven desde su dominio y `BUILD:"auto"` activa su SDK automáticamente.

## 🚀 Checklist de lanzamiento (paso a paso)

**A. Publicar el juego (gratis, ~5 min)**
- [ ] GitHub → repo → **Settings → Pages** → Source: *Deploy from a branch* → `main` / `/(root)` → Save.
- [ ] Esperar ~1 min. URL pública: `https://cristiiaanlp.github.io/ecos/`.
- [x] **Arte e iconos ya cableados:** `images/cover.png` (tarjeta social OG/Twitter), `icon-192/512.png` + `apple-touch-icon.png` (PWA/iOS, generados de `images/icono.png`). Sube `images/Thumbnail.png` como miniatura en el panel del portal.

**B. Anuncios (necesita aprobación, días/semanas)**
- [ ] Crear cuenta en **Google AdSense** y solicitar **H5 Games Ads** (requiere sitio propio con algo de tráfico; puede tardar en aprobarse).
- [ ] Cuando te aprueben, pegar tu ID en `CONFIG.ADSENSE_CLIENT` y volver a subir.

**C. Cobrar el "quitar anuncios" (cuenta Stripe verificada)**
- [ ] Crear cuenta **Stripe** (pide identidad y cuenta bancaria; verificación ~1-2 días).
- [ ] Stripe → **Payment Links** → enlace de 1,99 € → "Tras el pago" redirige a `GAME_URL?paid=1`.
- [ ] Pegar el enlace en `CONFIG.STRIPE_PAYMENT_LINK`.

**D. Tráfico (lo que de verdad da dinero)**
- [ ] Enviar a portales: **GameDistribution** e **itch.io** (entrada rápida), **CrazyGames** y **Poki** (revisión).
- [ ] Grabar clips cortos del "momento eco" para TikTok/Shorts/Reels.

> Resumen: el **código no hay que tocarlo** salvo pegar 2 valores en `CONFIG`. El resto son trámites de cuentas y, sobre todo, **conseguir jugadores**.

---

Hecho con 🩵 — un solo archivo, cero dependencias.
