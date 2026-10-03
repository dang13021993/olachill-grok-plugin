# OlaChill — Grok Build plugin

Official Grok Build plugin for [OlaChill](https://olachill.com) (MIA Co., Ltd., Kyoto, Japan).

This repository is the plugin shell only: manifest, one skill, and MCP client config.
Product data, prices and bookings stay on OlaChill. Nothing here executes local shell or reads secrets.

## What it adds

After install + trust, Grok Build attaches the hosted MCP server and the `olachill-travel` skill.

- Search and shortlist tours, activities, tickets and ryokan
- Check open dates for tours and tickets
- Helicopter sightseeing, private airport transfers, charter coaches
- Golf, chauffeured cars, Japan eSIM
- Booking / request status

## Network

| Endpoint | Why |
|---|---|
| `https://olachill.com/mcp` | Hosted Model Context Protocol server (tools listed below) |
| `https://olachill.com` | Product pages returned by tools |

No API key or local credentials are required, and the plugin reads no files or environment variables. Tools are read-only except `request_charter_quote`, which sends a quotation request only after the traveller confirms. It is not a booking and does not charge. The plugin ships no scripts, hooks, commands or binaries.

## Security / privacy

This repo contains no backend source, `.env`, API keys, database credentials, supplier rates, booking database, admin code or private source files. The plugin has no hooks, postinstall scripts or local executables.

## MCP tools (no auth)

`recommend_japan_travel_options`, `search_travel_products`, `check_product_availability`, `search_helicopter_experiences`, `search_private_transfers`, `search_charter_vehicles`, `get_charter_quote`, `request_charter_quote`, `search_golf_packages`, `search_chauffeur_services`, `search_esim_plans`, `get_booking_status`, `list_olachill_services`

## Install

```bash
grok plugin install dang13021993/olachill-grok-plugin --trust
```

Or from the official marketplace once the catalog PR is merged:

```bash
grok plugin install olachill --trust
```

## Layout

```
.grok-plugin/plugin.json      manifest
.mcp.json                     hosted MCP server (HTTP, no auth)
skills/olachill-travel/SKILL.md
assets/logo.png
LICENSE
README.md
```

## License

MIT. See [LICENSE](LICENSE).

## Support

- Product: [olachill.com](https://olachill.com)
- Contact: partners@olachill.com
- Privacy: https://olachill.com/en/privacy-policy
- Terms: https://olachill.com/en/terms-of-service
