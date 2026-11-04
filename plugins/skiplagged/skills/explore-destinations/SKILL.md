---
name: explore-destinations
description: Find cheap places to fly from a city when the user is flexible about where to go. Use when the user asks "where can I go", "cheapest places to fly from X", wants trip ideas for a budget, a weekend getaway, or travel inspiration for given dates.
---

# Explore cheap destinations with Skiplagged

Use the Skiplagged connector to show where the user can fly for the least money. Every price must come from a tool result in this conversation.

## 1. Collect what you need

Required: departure city and departure date. Optional: return date, number of travelers, cabin, budget, and the kind of place they want (beach, city, international, close by).

- If the user doesn't name a departure city, call `sk_resolve_location` and confirm the airport with them.
- For "next weekend" or "sometime in March", pick concrete `YYYY-MM-DD` dates and say which dates you used.
- Reply in the user's language and pass `currency` in their local currency when you can tell it.

## 2. Search

Call `sk_destinations_anywhere` with `from`, `depart`, and `return` if it's a round trip. Results come back sorted by price.

## 3. Present the results

Filter by what the user asked for (budget, region, type of place), then show 5–8 destinations: city and airport code, region, price, whether the fare is standard or hidden-city, and the **See flight** link from the result, unchanged. Group them if that helps, for example "Under $100" and "Under $200".

For hidden-city fares, follow the rules in the `find-flights` skill.

Offer a next step: search exact flights for one destination with `sk_flights_search`, or price the whole trip with the `plan-trip` skill.
