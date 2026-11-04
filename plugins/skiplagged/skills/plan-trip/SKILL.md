---
name: plan-trip
description: Plan and price a whole trip with Skiplagged, combining flights, a hotel, and optionally a rental car. Use when the user asks to plan a trip or vacation, wants a trip budget or total cost, asks "how much would a trip to X cost", or wants flights and a hotel together.
---

# Plan a trip with Skiplagged

Put together a complete, priced trip from real Skiplagged results: flights there and back, a hotel for the nights in between, and a rental car if the user needs one. Every price must come from a tool result in this conversation.

## 1. Collect the trip basics

Ask in one message for anything missing:

- Where from and where to.
- Dates, or a month and trip length if they're flexible.
- Number of travelers (adults and children).
- Budget, if they have one, and what matters most: lowest price, comfort, or location.
- Whether they need a car.

Reply in the user's language and pass `currency` in their local currency when you can tell it.

## 2. Find the flights

Follow the `find-flights` skill.

- If dates are flexible, use `sk_flex_return_calendar` first to find the cheapest date pair for the trip length.
- For a hidden-city fare, search each direction as a one-way, as `find-flights` explains.

## 3. Find the hotel

Follow the `find-hotels` skill. Check in on the outbound arrival date and check out on the return date. Search in the city the user is actually visiting. For a hidden-city fare, that's the layover city, not the ticket's final destination.

## 4. Find a car, if needed

Follow the `find-rental-cars` skill. Pick up at the arrival airport about an hour after the outbound flight lands, and drop off a couple of hours before the return flight.

## 5. Present the plan

Give a short itinerary and a cost table:

| Item | Choice | Price | Link |
| --- | --- | --- | --- |
| Outbound flight | … | … | Book |
| Return flight | … | … | Book |
| Hotel (N nights) | … | … | View deal |
| Rental car | … | … | Book |
| **Total** | | **…** | |

- Add the prices from the tool results. Say that the total is an estimate and that taxes or fees shown at checkout can differ.
- If the total is over the user's budget, offer one or two concrete ways to save, such as a cheaper date from the calendar, a hidden-city fare, or a lower-priced hotel, and search again if they want.
- Use every booking link unchanged. You can't book or pay for the user. Booking happens on skiplagged.com.
