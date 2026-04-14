# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

Static HTML documentation site for Ari's Integration APIs, titled "API's de Integración". Pre-rendered Redoc (OpenAPI/Swagger) output that documents all external-facing REST APIs used by third-party integrators connecting to the Ari platform.

- **Type:** web (documentation site)
- **Domain:** integration
- **Rendered with:** Redoc v2.5.0 (Redocly)

## Architecture

The repository contains a single self-contained artifact: `index.html` (~2 MB). There is no build tooling, no `package.json`, no source OpenAPI spec (YAML/JSON) in this repo — the HTML is a fully pre-rendered Redoc export generated elsewhere and committed directly.

Consequences for editing:
- Changes to API documentation are made by regenerating `index.html` externally and replacing the file. Do not hand-edit CSS/JS inside it.
- The version string (e.g. `1.0.2`) appears inline in `index.html` around line 450 — update it when a new rendered version is committed.
- `catalog-info.yaml` registers this component in Backstage (`arigroup/apis-integration-and-webhook`, `requires_human_review: true`).
- `.github/workflows/catalog-sync.yml` syncs the Backstage catalog entry.

## What the Documentation Covers

Organized by tag/service, all hosted under `https://integration.arisale.com.pe/`:

| Tag | Service path |
|-----|--------------|
| Local | `local-service/api` |
| Area | `area-service/api` |
| Impuestos | `tax-service/api` |
| Categoria | `category-service/api` |
| Marca | `brand-service/api` |
| Variantes | `variant-service/api` |
| Modificador | `modifier-service/api` |
| Producto | `product-service/api` |
| Inventario | `inventory-service/api` |
| Ingrediente | `ingredients-service/api` |
| Receta | `recipes-service/api` |
| Cpe | `cpe-service/api` |

Webhooks documented: `webhook-sale` (registro de venta) and `webhook-cpe` (registro de CPE).

All endpoints require the `api-key` header.

### Integration order (as documented in the site)

1. Locales
2. Áreas, Impuestos, Categorías, Marcas, Variantes, Modificadores (reference data)
3. Productos
4. Inventario
5. CPE / Ventas

## Local Preview

No build step. Open `index.html` directly in a browser, or serve the directory with any static server (e.g. `python3 -m http.server`).
