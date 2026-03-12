# apis-integration-and-webhook

## Purpose
This repository contains the static HTML documentation site for Ari's Integration APIs. It is a pre-rendered Redoc (OpenAPI/Swagger) documentation page titled "API's de Integración" (version 1.0.2). The site documents all external-facing REST APIs that third-party integrators use to connect with the Ari platform.

## Type
- **Type:** web (documentation site)
- **Domain:** integration
- **Language:** HTML (single-file static site)
- **Rendered with:** Redoc v2.5.0 (Redocly)

## What It Documents
The site covers the full integration API surface for Ari, organized by service/tag:

| Tag | Description |
|-----|-------------|
| Local | Consulta locales (stores) |
| Area | Gestión de áreas |
| Impuestos | Listado de impuestos |
| Categoria | Categorías y subcategorías de productos |
| Marca | Marcas de productos |
| Variantes | Tipos de variantes y variantes |
| Modificador | Grupos de modificadores, modificadores, traducciones |
| Producto | Creación, actualización y consulta de productos |
| Inventario | Gestión de existencias (incrementar, decrementar, consultar) |
| Ingrediente | Ingredientes para recetas |
| Receta | Recetas y categorías de receta |
| Cpe | Comprobantes de pago electrónicos (CPE) |
| Webhook | Webhooks de registro de venta y CPE |

## API Base URLs (per service)
All services are hosted under `https://integration.arisale.com.pe/`:
- `area-service/api`
- `brand-service/api`
- `category-service/api`
- `cpe-service/api`
- `ingredients-service/api`
- `inventory-service/api`
- `local-service/api`
- `modifier-service/api`
- `product-service/api`
- `recipes-service/api`
- `tax-service/api`
- `variant-service/api`

## Webhooks
Two webhook events are documented:
- **webhook-sale**: Webhook de registro de venta
- **webhook-cpe**: Webhook de registro de comprobante de pago electrónico

## Authentication
All endpoints require `api-key` header authorization.

## Integration Order (as documented)
The site includes a guide "Guia de Integración: El orden correcto para conectar con Ari" with a recommended integration sequence:
1. Locales
2. Áreas, Impuestos, Categorías, Marcas, Variantes, Modificadores (reference data)
3. Productos
4. Inventario
5. CPE / Ventas

## Notes
- The entire documentation is contained in a single `index.html` file (~1.8 MB pre-rendered).
- No build tooling, package.json, or source files are present — the file is a fully self-contained static export.
- **requires_human_review: true** — The repository contains only a rendered HTML file. The underlying OpenAPI spec source (YAML/JSON) is not present in this repo.
