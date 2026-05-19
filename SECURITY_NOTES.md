# Notas de seguridad

Esta demo es estática y no debe usarse como sistema productivo sin rediseño de seguridad.

## Lo que sí evita esta demo

- No usa PHP.
- No usa jQuery ni librerías obsoletas.
- No transmite credenciales por red.
- No usa endpoints falsos de autenticación.
- No carga scripts por HTTP.
- Usa `charset="UTF-8"`.
- Usa `rel="noopener noreferrer"` en enlaces externos o nuevas pestañas.
- No incluye datos simulados como si fueran hechos reales.

## Recomendaciones para producción

Implementar autenticación real del lado servidor, control de roles, bitácora auditada, cifrado en tránsito con HTTPS obligatorio, almacenamiento seguro, validación de archivos, antivirus/sandbox para PDFs, OCR controlado, monitoreo, rate limiting y revisión legal de tratamiento de datos personales.

## Cabeceras sugeridas

```http
Content-Security-Policy: default-src 'self'; object-src 'self'; frame-ancestors 'none'; base-uri 'self'; form-action 'self'
X-Frame-Options: DENY
X-Content-Type-Options: nosniff
Referrer-Policy: no-referrer
Permissions-Policy: geolocation=(), microphone=(), camera=(), payment=()
Cache-Control: no-store
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

## Unknown unknowns

- Cambios en formato de boletines futuros pueden romper la extracción.
- Algunas páginas escaneadas pueden requerir OCR y controles de calidad adicionales.
- Nombres homónimos pueden generar falsos positivos.
- La paginación impresa y la página real del PDF pueden diferir en otros boletines.
- La publicación judicial puede contener datos personales; se requiere evaluación jurídica de finalidad, proporcionalidad y minimización.
