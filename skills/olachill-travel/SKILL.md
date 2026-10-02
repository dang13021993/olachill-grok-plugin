---
name: olachill-travel
description: Use OlaChill Travel MCP tools to find bookable Japan products (tours, activities, tickets, ryokan, helicopter, airport transfers, charter coaches, golf, chauffeured cars, eSIM) and check booking status. Trigger when the user mentions OlaChill or asks to look up OlaChill products on olachill.com.
---

# OlaChill Travel

Hosted MCP server: `https://olachill.com/mcp` (no auth). Tools run on OlaChill infrastructure. This plugin ships no local scripts.

## Tools

Use the most specific tool:

| Need | Tool |
|---|---|
| Shortlist from preferences | `recommend_japan_travel_options` |
| Named place / product / type | `search_travel_products` then `check_product_availability` for dates |
| Helicopter sightseeing | `search_helicopter_experiences` |
| Private airport car (1–6 people) | `search_private_transfers` |
| Group bus / coach / minibus | `search_charter_vehicles` then `get_charter_quote` |
| Send a charter quote request | `request_charter_quote` only after explicit user confirmation |
| Golf | `search_golf_packages` |
| Chauffeur by day/hour | `search_chauffeur_services` |
| Japan eSIM | `search_esim_plans` |
| Existing booking / request | `get_booking_status` |
| Other OlaChill services | `list_olachill_services` |

## Rules

1. Call tools before inventing products, prices, or availability.
2. Always include the `product_url` from the tool. Prices are "from" / estimates. Final price, dates and payment happen on olachill.com.
3. Do not take payment or complete a booking in chat.
4. Do not call `request_charter_quote` until the user explicitly confirms sending the request. That action is not a booking and charges nothing.
5. Out of scope: hotels (except ryokan), airline flights, restaurant reservations, rail timetables, weather, visas, general destination advice with no bookable product.

## Style

- Ask for city, date, party size and interests when missing.
- Return 2–5 options with match reason, "from" price and link.
- Note caveats (seat vs whole aircraft, private onsen, on_request vs on_sale).
- Next step: open the product page, check dates, or confirm a quote request.
