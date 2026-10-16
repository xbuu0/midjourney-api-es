# Midjourney API (`midjourney`)

<!-- conv-kit:v1 -->

<p align="center">
  <img src="assets/badges/price.svg" alt="observed unit price"> <img src="assets/badges/billing.svg" alt="billing model"> <img src="assets/badges/compat.svg" alt="OpenAI-compatible endpoint">
</p>

<p align="center">
  <img src="assets/01-product-hero-perfume.jpg" width="820" alt="Sample render via the APIMart image API">
</p>

> **from $0.045 per image** on the APIMart route — un único endpoint compatible con OpenAI en `https://api.apimart.ai/v1`, sin plan mensual. *(observado el 2026-10-12)*

**[Obtener una clave de API](https://go.apimart.ai/k-3e40fe)** · **[Precios en vivo](https://go.apimart.ai/k-8aecd2)** · **[Página del modelo](https://go.apimart.ai/k-1416cd)** · [⚡ Inicio rápido en 60 segundos](#quickstart)

**Por qué los equipos usan Midjourney (`midjourney`) a través de APIMart**

- **Una clave, todo el catálogo.** La misma base URL `https://api.apimart.ai/v1` y la misma cabecera `Authorization` dan acceso a Midjourney (`midjourney`) y a más de 300 modelos de imagen, vídeo y lenguaje: cambia el campo `model`, no tu cliente.
- **Mínimo de $1, pago por uso.** Sin suscripción ni plan prepago que dimensionar por adelantado: recarga desde $1 y úsalo en llamadas.
- **El cargo vuelve en la respuesta.** Cada tarea completada informa del importe facturado (`cost` / `credits_cost`); una tarea marcada como `failed` se reembolsa.
- **Asíncrono por diseño.** Envía, toma el `task_id`, consulta `GET /v1/tasks/{id}`: el batching y los reintentos son trabajo de cola normal, no una integración a medida.

<!-- /conv-kit:v1 -->



Midjourney is the industry-leading text-to-image engine, prized for its painterly aesthetic, strong composition, and signature lighting. APIMart exposes Midjourney as a programmable API — call /v1/midjourney/generations for the default Imagine flow, choose v8.1, v7, v6.1, v5.2, v5.1 or Niji 7 / Niji 6, dial in stylize / chaos / weird, and run on relax, fast, or turbo queues without touching Discord.

## Model id and routes

| Route | `model` value | Billing | Notes |
| --- | --- | --- | --- |
| Per-image | `midjourney` | per delivered image, by resolution | see the [model page](https://go.apimart.ai/k-1416cd) for the exact tiers |

Endpoint: `POST https://api.apimart.ai/v1/images/generations`, then poll `GET /v1/tasks/{task_id}`.

## Pricing

<!-- pricing:model:start -->
| Output | List price | Effective price |
| --- | --- | --- |
| default | 0.0563 | 0.04504 |
| blend | 0.0688 | 0.05504 |
| blend-fast | 0.0688 | 0.05504 |
| blend-turbo | 0.125 | 0.1 |
| describe | 0.0688 | 0.05504 |
| describe-fast | 0.0688 | 0.05504 |
| describe-turbo | 0.125 | 0.1 |
| edits | 0.0688 | 0.05504 |
| edits-fast | 0.0688 | 0.05504 |
| edits-turbo | 0.125 | 0.1 |
| high_variation | 0.0688 | 0.05504 |
| high_variation-fast | 0.0688 | 0.05504 |
| high_variation-turbo | 0.125 | 0.1 |
| imagine | 0.0563 | 0.04504 |
| imagine-fast | 0.0688 | 0.05504 |
| imagine-niji6 | 0.0563 | 0.04504 |
| imagine-niji6-fast | 0.0688 | 0.05504 |
| imagine-niji6-turbo | 0.125 | 0.1 |
| imagine-niji7 | 0.0563 | 0.04504 |
| imagine-niji7-fast | 0.0688 | 0.05504 |
| imagine-niji7-turbo | 0.125 | 0.1 |
| imagine-turbo | 0.125 | 0.1 |
| imagine-v5.1 | 0.0563 | 0.04504 |
| imagine-v5.1-fast | 0.0688 | 0.05504 |
| imagine-v5.1-turbo | 0.125 | 0.1 |
| imagine-v5.2 | 0.0563 | 0.04504 |
| imagine-v5.2-fast | 0.0688 | 0.05504 |
| imagine-v5.2-turbo | 0.125 | 0.1 |
| imagine-v6.1 | 0.0563 | 0.04504 |
| imagine-v6.1-fast | 0.0688 | 0.05504 |
| imagine-v6.1-turbo | 0.125 | 0.1 |
| imagine-v7 | 0.0563 | 0.04504 |
| imagine-v7-fast | 0.0688 | 0.05504 |
| imagine-v7-turbo | 0.125 | 0.1 |
| imagine-v8.1 | 0.0563 | 0.04504 |
| imagine-v8.1-fast | 0.0688 | 0.05504 |
| imagine-v8.1-turbo | 0.125 | 0.1 |
| imagine-v8.2 | 0.0563 | 0.04504 |
| imagine-v8.2-fast | 0.0688 | 0.05504 |
| imagine-v8.2-turbo | 0.125 | 0.1 |
| inpaint | 0.0688 | 0.05504 |
| inpaint-fast | 0.0688 | 0.05504 |
| inpaint-turbo | 0.125 | 0.1 |
| low_variation | 0.0688 | 0.05504 |
| low_variation-fast | 0.0688 | 0.05504 |
| low_variation-turbo | 0.125 | 0.1 |
| modal | 0.0688 | 0.05504 |
| modal-fast | 0.0688 | 0.05504 |
| modal-turbo | 0.125 | 0.1 |
| pan | 0.0688 | 0.05504 |
| pan-fast | 0.0688 | 0.05504 |
| pan-turbo | 0.125 | 0.1 |
| remix_strong | 0.0688 | 0.05504 |
| remix_strong-fast | 0.0688 | 0.05504 |
| remix_strong-turbo | 0.125 | 0.1 |
| remix_subtle | 0.0688 | 0.05504 |
| remix_subtle-fast | 0.0688 | 0.05504 |
| remix_subtle-turbo | 0.125 | 0.1 |
| reroll | 0.0688 | 0.05504 |
| reroll-fast | 0.0688 | 0.05504 |
| reroll-turbo | 0.125 | 0.1 |
| shorten | 0.0688 | 0.05504 |
| shorten-fast | 0.0688 | 0.05504 |
| shorten-turbo | 0.125 | 0.1 |
| upscale-hd | 0.0688 | 0.05504 |
| upscale-hd-fast | 0.0688 | 0.05504 |
| upscale-hd-turbo | 0.125 | 0.1 |
| variation | 0.0688 | 0.05504 |
| variation-fast | 0.0688 | 0.05504 |
| variation-turbo | 0.125 | 0.1 |
| video | 0.25 | 0.2 |
| video-720p | 0.5 | 0.4 |
| zoom | 0.0688 | 0.05504 |
| zoom-fast | 0.0688 | 0.05504 |
| zoom-turbo | 0.125 | 0.1 |


<!-- pricing:model:end -->

Prices are a snapshot; the [pricing page](https://go.apimart.ai/k-8aecd2) and [`data/model.json`](data/model.json) are refreshed by CI, and a completed task reports the exact amount in its `cost` field.

## Request parameters

| Field | Type | Default | Notes |
| --- | --- | --- | --- |
| `model` | string | required | the model id shown in the route table above |
| `prompt` | string | required | what to generate, or what to change when editing |
| `size` | string | `auto` / `1:1` | aspect ratio, or `auto` where the route supports it |
| `resolution` | string | `1K` | output resolution tier — cost scales with it |
| `n` | integer | `1` | number of images per task, where the route allows more than one |
| `image_urls` | string[] | — | reference images as public HTTP(S) URLs or base64 data URLs |
| `nsfw_check` | boolean | `false` | runs `omni-moderation-latest` before submitting |

The table lists the fields accepted by the APIMart `images/generations` endpoint. Check the [model page](https://go.apimart.ai/k-1416cd) for anything this model adds on top.

## Quickstart

```bash
curl --request POST --url https://api.apimart.ai/v1/images/generations \
  --header "Authorization: Bearer $APIMART_API_KEY" --header 'Content-Type: application/json' \
  -d '{"model":"midjourney","prompt":"A bamboo forest at sunrise, slow push-in","size":"1:1","resolution":"1K"}'
```

```python
import os, time, requests

BASE = "https://api.apimart.ai/v1"
HEADERS = {"Authorization": f"Bearer {os.environ['APIMART_API_KEY']}", "Content-Type": "application/json"}

created = requests.post(f"{BASE}/images/generations", headers=HEADERS, timeout=60, json={
    "model": "midjourney", "prompt": "A bamboo forest at sunrise, slow push-in",
}).json()
task_id = created["data"]["id"]

while True:
    task = requests.get(f"{BASE}/tasks/{task_id}", headers=HEADERS, timeout=60).json()["data"]
    if task["status"] in ("completed", "failed"):
        break
    time.sleep(5)
print(task.get("cost"), task["result"]["images"][0]["url"])
```

Runnable versions: [`examples/`](examples). The task lifecycle is `pending → processing → completed | failed`.

## FAQ

**¿Cuál es el id del modelo Midjourney?**

`midjourney`. Consulta la tabla de rutas de arriba.

**¿Cómo se factura?**

**from $0.045 per image** on the APIMart route. La tarea completada informa del importe exacto en su campo `cost`; una tarea fallida se reembolsa.

**How do I get a key?**

Use the [Get an API key](https://go.apimart.ai/k-3e40fe) link — $1 minimum top-up, no plan required.

<!-- related-repos:auto -->
## Related repositories

- **Same model, this language** — the other half of this pair: [midjourney-prompts-es](https://github.com/xbuu0/midjourney-prompts-es)
- **Same model, other languages** — 9 more language builds: 中文 [midjourney-api-cn](https://github.com/apimartycl6k972t/midjourney-api-cn) · Deutsch [midjourney-api-de](https://github.com/h5fd0cofy/midjourney-api-de) · Français [midjourney-api-fr](https://github.com/apimartt1q/midjourney-api-fr) · Relay/gateway [midjourney-api-gateway](https://github.com/apimartxc3iskw/midjourney-api-gateway) · Bahasa [midjourney-api-id](https://github.com/cvrwq0/midjourney-api-id) · 日本語 [midjourney-api-ja](https://github.com/apimartt1q/midjourney-api-ja) · 한국어 [midjourney-api-ko](https://github.com/ocvewn2-9ueo/midjourney-api-ko) · Português [midjourney-api-pt](https://github.com/l-ca0/midjourney-api-pt) · Русский [midjourney-api-ru](https://github.com/sfpxvicw/midjourney-api-ru)
- **More models in this language** — [gemini-2-5-flash-image-preview-api-es](https://github.com/ekw3w/gemini-2-5-flash-image-preview-api-es) · [nano-banana-api-es](https://github.com/gbm5mfl1/nano-banana-api-es) · [gemini-3-1-flash-image-preview-api-es](https://github.com/x3kcczm8l29xn/gemini-3-1-flash-image-preview-api-es) · [nano-banana-2-api-es](https://github.com/d63hy9t-4pp/nano-banana-2-api-es) · [gemini-3-pro-image-preview-api-es](https://github.com/uv9d8/gemini-3-pro-image-preview-api-es) · [nano-banana-pro-api-es](https://github.com/g6-erqods5/nano-banana-pro-api-es)
- **Topic hubs** — every build of this model, all languages: [midjourney](https://github.com/topics/midjourney) · [midjourney-api](https://github.com/topics/midjourney-api)

This repository is one build in a cross-linked set of API guides for the same model family; each language build links back to the others.
<!-- /related-repos:auto -->

## Attributed links (how this repository is measured)

| Purpose | Attributed link | Target |
| --- | --- | --- |
| Model page | <https://go.apimart.ai/k-1416cd> | `apimart.ai/es/model/midjourney` |
| Live pricing | <https://go.apimart.ai/k-8aecd2> | `apimart.ai/es/pricing` |
| Get an API key | <https://go.apimart.ai/k-3e40fe> | `apimart.ai/es/keys` |

Outbound APIMart links are minted through the promo link API; hand-made tracking parameters are rejected by
`tools/check_links.py` in CI.

## Disclosure

Midjourney is a third-party model served through APIMart; this repository documents how to call it and publishes
model ids and prices, and does not claim official status. Model names, prices and documentation belong to their
respective owners.

## License

MIT — see [LICENSE](LICENSE).
