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

## 💰 Activar anuncios reales (monetización)

El juego trae una pista (💡) que se desbloquea viendo un anuncio recompensado. Por defecto el anuncio está **simulado**. Para activar anuncios reales con Google AdSense for Games (H5):

1. Crea una cuenta en **Google AdSense** y activa **H5 Games Ads**.
2. En `index.html`, busca `const ADSENSE_CLIENT = ""` y pega tu ID de editor: `"ca-pub-XXXXXXXXXXXXXXXX"`.
3. Sube el juego a tu dominio **https** (GitHub Pages sirve) y espera la aprobación.

Si `ADSENSE_CLIENT` está vacío o el script no carga, se usa automáticamente el anuncio simulado (no rompe nada). El punto de recompensa es la función `onReward()`.

> El dinero depende del **tráfico**: para ingresos serios, publica también en portales (CrazyGames, Poki, GameDistribution).

---

Hecho con 🩵 — un solo archivo, cero dependencias.
