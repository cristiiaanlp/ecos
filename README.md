# 🌀 ECOS

> Coordínate con tus yos del pasado.

Un puzzle web sobre el **tiempo**: cuando te atascas, creas un **eco** que repite tus movimientos anteriores. Así un "tú" del pasado mantiene un botón pisado mientras el "tú" del presente cruza la puerta.

**▶ Jugar:** abre `index.html` en cualquier navegador (o publícalo con GitHub Pages).

## Características

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

## 💰 Monetización (todo preparado, solo faltan credenciales)

Todas las credenciales están en **un único bloque `CONFIG`** al principio del `<script>` de `index.html`. Mientras estén vacías, todo funciona en modo **simulado** (no cobra, no rompe nada).

```js
const CONFIG = {
  ADSENSE_CLIENT:      "",   // "ca-pub-XXXXXXXXXXXXXXXX"
  STRIPE_PAYMENT_LINK: "",   // "https://buy.stripe.com/xxxxxxxx"
  GAME_URL:            "https://cristiiaanlp.github.io/ecos/"
};
```

**1) Anuncios (AdSense for Games / H5)** — pista recompensada (💡) + intersticial cada 3 niveles.
- Crea cuenta en **Google AdSense**, activa **H5 Games Ads** y pega tu ID en `ADSENSE_CLIENT`.
- Sube el juego a tu dominio **https** y espera la aprobación.

**2) Quitar anuncios (1,99 €) con Stripe** — sin servidor, usando un **Payment Link**.
- En Stripe → **Payment Links**, crea un enlace de 1,99 €.
- En "Tras el pago", redirige a `GAME_URL` + `?paid=1`.
- Pega ese enlace en `STRIPE_PAYMENT_LINK`.
- Al volver con `?paid=1`, el juego activa "sin anuncios" (quita intersticiales y la pista pasa a ser gratis).
- ⚠️ Es un desbloqueo del lado cliente (suficiente para un extra de 1,99 €). Para verificación 100% fiable haría falta un backend con webhook de Stripe.

> El dinero depende del **tráfico**: para ingresos serios, publica también en portales (CrazyGames, Poki, GameDistribution).

---

Hecho con 🩵 — un solo archivo, cero dependencias.
