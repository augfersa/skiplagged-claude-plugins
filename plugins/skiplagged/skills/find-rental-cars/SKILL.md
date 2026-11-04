---
name: find-rental-cars
description: Search for rental cars with Skiplagged. Use when the user needs a car at their destination, asks for car rental prices, cheap rental cars at an airport or city, or one-way car rentals between two places.
---

# Find rental cars with Skiplagged

Use the Skiplagged connector to find real rental-car offers. Every price, company, and car detail you show must come from a tool result in this conversation.

## 1. Collect what you need

Required: pickup location, pickup date, drop-off date. Optional: pickup and drop-off times, a different drop-off location, car size, number of passengers and bags.

- An airport code (`MIA`) or a city name works for the location.
- Times use 24-hour `HH:mm` and default to `10:00`. If the user is arriving on a flight, set `pickupTime` to about an hour after the flight lands.
- Leave `dropoffLocation` empty to return the car where it was picked up. Set it for one-way rentals.
- Reply in the user's language.

## 2. Search

Call `sk_cars_search`. If the user wants more options, call again with `offset`.

## 3. Present the results

Show 3–5 offers: company, car class, passengers and bags, whether payment is now or at the counter, the total price, and the **Book** link from the result, unchanged. Filter out cars too small for the party the user described. Add a one-line recommendation.

Mention that "pay at counter" prices may not include local taxes or extras such as insurance or a young-driver fee, and that the user should check the details on the booking page.

You can't book or pay for the user. Booking happens on skiplagged.com via the link.
