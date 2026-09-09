# NovaBank — Banco Virtual

Banco virtual con pagos QR y transferencias interbancarias, diseñado
bajo un sistema de diseño propio (three-token color system, tipografía
dual Manrope/DM Sans) y validado con principios de usabilidad Nielsen
y WCAG 2.1 AA.

## Vista previa

[Capturas de las 24 pantallas o GIF de flujo principal]

## Arquitectura del proyecto

NovaBank se organiza en repositorios independientes:

| Repositorio          | Responsabilidad                                                                |
| -------------------- | ------------------------------------------------------------------------------ |
| `NovaBank_API`     | Núcleo del sistema — APIs de cuentas, transferencias, OTP, seguridad         |
| `NovaBank_app`     | Banca virtual del cliente (frontend móvil/web consumido por el usuario final) |
| `NovaBank_soporte` | Monitoreo de integridad, trazabilidad de operaciones y seguridad               |
| `NovaBank_web`     | Landing page del producto                                                      |

## Sistema de diseño

- **Paleta:** 3 colores de marca + 3 semánticos, con tokens (`T.surf`,
  `T.ink`, `T.line`, `T.gold`) que conmutan automáticamente entre modo
  claro y oscuro.
- **Tipografía:** Cormorant Garamond (wordmark), Manrope (montos y
  títulos), DM Sans (cuerpo y metadatos).
- **Iconografía:** Material Symbols Rounded, set único en toda la app.
- **Accesibilidad:** contraste mínimo 4.5:1 en texto, 3:1 en titulares,
  verificado en ambos temas (ver 4.c, punto 8).

## Navegación

- Zona pública sin sesión (bienvenida, registro, OTP, login, recuperación).
- Barra de pestañas inferior con 5 destinos (Inicio, Movimientos,
  Transferir, Alertas, Perfil).
- Pantallas de detalle accedidas desde el dashboard, perfil o pestañas.

Detalle completo de flujos en la sección 4.d de este documento.

## Requisitos previos

- Node.js >= 18
- [gestor de paquetes: npm / pnpm]
- Variables de entorno (ver `.env.example`)
- Acceso a la base de datos [motor a especificar]

## Instalación

\`\`\`bash
git clone [github.com/JamesRedzafiro/Proyecto_Integrador_II](https://github.com/JamesRedzafiro/Proyecto_Integrador_II)
cd NovaBank_app
npm install
cp .env.example .env
npm run dev
\`\`\`

## Seguridad

- Autenticación biométrica local (no sale del dispositivo).
- OTP de 6 dígitos para operaciones sensibles.
- Bloqueo por intentos fallidos (temporizador de 30 min).
- Cierre remoto de sesiones desde Centro de seguridad.

## Testing

[Framework de pruebas usado, comando de ejecución, cobertura mínima]

## Licencia

© NovaBank. Todos los derechos reservados.
