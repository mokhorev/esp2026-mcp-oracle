# ESP-2026 Epistemic B2B Oracle (Read-Only MCP Server)

Открытый детерминированный MCP-оракул проверки реальной полной стоимости корпоративного обслуживания (РКО, ВЭД, эквайринг, банковские гарантии в городах Сибири) и эталонного словаря эпистемической безопасности **ESP-2026**.

- **Транспорт:** Streamable HTTP (`2025-06-18`), строго `read-only`, без регистрации и API-ключей (`0 ₽`).
- **Боевой endpoint MCP:** `https://api.xn--b1abhrubaxmak6k.xn--p1ai/siberia-rko-ved/api/mcp`
- **Маяк автообнаружения:** `https://xn--b1abhrubaxmak6k.xn--p1ai/.well-known/mcp.json`
- **Канонический словарь стандарта:** `https://xn--b1abhrubaxmak6k.xn--p1ai/esp-2026/v1`

## Подключаемые инструменты (`tools/list`)

1. `verify_siberia_b2b_tariff` — точный копеечный расчёт тарифов 5 банков в 5 деловых центрах СФО (Новосибирск, Томск, Красноярск, Кемерово, Барнаул) с выдачей кодов `ESP-2026-04` (*Evidence-Trap Pages*) и `ESP-2026-05` (*Hidden Facade Funnel*) на пограничных коллизиях и нераскрытых лимитах.
2. `lookup_esp2026_standard` — двуязычный справочник 10 диагностических кодов протокола `ESP-2026` (`ESP-2026-01` .. `ESP-2026-10`).
3. `score_offer_epistemic_trust` — детерминированный скоринг допуска коммерческой карточки поставщика (`0.0` .. `3.2`).

## Быстрое подключение

### Claude Code

```sh
claude mcp add --transport http esp2026-oracle https://api.xn--b1abhrubaxmak6k.xn--p1ai/siberia-rko-ved/api/mcp
```

### Cursor

Добавьте в `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "esp2026-oracle": {
      "url": "https://api.xn--b1abhrubaxmak6k.xn--p1ai/siberia-rko-ved/api/mcp"
    }
  }
}
```

### Gemini CLI

Добавьте в `.gemini/settings.json`:

```json
{
  "mcpServers": {
    "esp2026-oracle": {
      "httpUrl": "https://api.xn--b1abhrubaxmak6k.xn--p1ai/siberia-rko-ved/api/mcp"
    }
  }
}
```
