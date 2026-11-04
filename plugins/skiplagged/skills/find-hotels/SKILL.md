---
name: find-hotels
description: Search for hotels and accommodation deals with Skiplagged. Use when the user needs a place to stay, asks for hotel prices, cheap or highly rated hotels in a city, compares hotels for specific dates, or wants room details and amenities for a hotel.
---

# Find hotels with Skiplagged

Use the Skiplagged connector to find real hotel prices. Every price, rating, and amenity you show must come from a tool result in this conversation.

## 1. Collect what you need

Required: city, check-in date, check-out date. Optional: number of rooms, adults, children, budget, neighborhood, star rating, must-have amenities.

- If dates are missing, ask in one short question. Turn relative dates ("this Friday to Sunday") into `YYYY-MM-DD` and say which dates you used.
- `numAdults` defaults to 2. Set it to 1 for a solo traveler.
- Pass `currency` in the user's local currency when you can tell it. Reply in the user's language.

## 2. Search

Call `sk_hotels_search` with `city`, `checkin`, `checkout`, and the party size. Choose `sort` from what the user cares about:

- `discount` for the best deals compared with the usual price.
- `price` for the cheapest.
- `ranking` for the best-rated.
- `value` for the best balance of price and quality (default).

If the user wants more choices, call again with `offset` to get the next page.

## 3. Present the results

Show 3–5 hotels: name, area or address, star rating and guest score, price per night, total for the stay, two or three key amenities, and the **View deal** link from the result, unchanged. Add a one-line recommendation that fits what the user asked for (cheapest, best-rated, best location).

If the connector renders interactive results, keep your text short and add only the recommendation.

## 4. Room details

When the user picks a hotel or asks about rooms, cancellation, or what's included, call `sk_hotel_details` with the `hotelId` from the search result and the same dates and party size. Leave `live` on so the result includes booking links. Summarize the room types, prices, and policies that matter to the user.

You can't book or pay for the user. Booking happens on skiplagged.com via the link.
