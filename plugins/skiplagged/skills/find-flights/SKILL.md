---
name: find-flights
description: Search for flights and airfare with Skiplagged. Use when the user wants to fly somewhere, asks for cheap flights, plane tickets, airfare prices, the best day to fly, nonstop options, or compares flight prices between cities or dates, including one-way, round-trip, and flexible-date trips.
---

# Find flights with Skiplagged

Use the Skiplagged connector's tools to find real, bookable fares. Never invent prices, times, or airlines; every number you show must come from a tool result in this conversation.

## 1. Collect what you need

Required: origin, destination, departure date. Optional: return date, number of travelers, cabin, stops, airline or time preferences.

- If a required value is missing, ask for it in one short question. If the user says "next weekend" or "mid-December", turn it into concrete `YYYY-MM-DD` dates and say which dates you used.
- If the user doesn't name an origin, call `sk_resolve_location` to find the nearest airport, and confirm it with them.
- City names are fine for `origin` and `destination` (for example `NYC`, `London`). If a city is ambiguous, call `sk_resolve_iata` first.
- Pass `currency` in the user's local currency when you can tell it (for example `EUR`, `GBP`, `MXN`, `BRL`). Reply in the user's language.

## 2. Pick the right tool

| The user's situation | Tool |
| --- | --- |
| Fixed dates | `sk_flights_search` |
| "When is it cheapest?" / flexible by a few days, one-way | `sk_flex_departure_calendar` |
| Flexible round trip with a set trip length | `sk_flex_return_calendar` |
| Doesn't know where to go | Use the `explore-destinations` skill |

When dates are flexible, run the calendar first, point out the 2–3 cheapest dates, then run `sk_flights_search` on the date the user picks (or the cheapest one, if they asked you to choose).

Useful `sk_flights_search` options:

- `sort`: `value` (default, best price for the time), `price`, or `duration`.
- `maxStops`: `none` for nonstop only, `one`, or `many`.
- `fareClass`: `basic-economy`, `economy`, `premium`, `business`, `first`.
- `adults`, `children`, `infantsLap`, `infantsSeat` for group size.
- `preferredAirlines` / `excludedAirlines` as two-letter codes (`["DL"]`).
- `departureTimeEarliest` / `departureTimeLatest` in minutes from midnight (e.g. 7 a.m. = 420).
- `maxLayoverDuration` in minutes, when the user dislikes long layovers.
- `includeHiddenCity: false` when the user wants to check bags, is booking a round trip they must complete, or asks for standard tickets only.

## 3. Present the results

Show the 3–5 best options in a compact table or list: price, total duration, stops, airline, departure and arrival times, and a **Book** link. Then add a one-line recommendation (cheapest, fastest, best value).

- Use each flight's `deepLink` (the **Book** link from the tool result) unchanged. Also offer the "Open search on Skiplagged" link so the user can see every option.
- Point out trade-offs honestly: a much cheaper fare with a 10-hour layover should be described as such.
- Don't paste the raw tool output. If the connector renders interactive results, keep your text short and add only the recommendation.
- You can't book or pay for the user. Booking happens on skiplagged.com via the link.

## 4. Hidden-city ("Skiplagging") fares

Results with the type **Skiplagging** or the attribute `hidden-city` are hidden-city fares: the ticket continues past the user's destination, and the user gets off at the layover. They're often the cheapest option, so include them when they're competitive. Every time you show one, label it clearly and give the short rules in `references/hidden-city.md`. Read that file before you explain hidden-city fares in detail.

## 5. Questions about Skiplagged itself

For questions about policies, bags, refunds, the Skiplagged Guarantee, or how hidden-city works, call `sk_faq_search` and answer from the articles it returns, with their links. Don't answer policy questions from memory.
