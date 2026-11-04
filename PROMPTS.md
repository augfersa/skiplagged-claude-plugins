# Use Skiplagged in Claude with a prompt

Copy one of these prompts into a chat with Claude. They work whether or not you've added the Skiplagged connector:

- **With the connector**, Claude searches live Skiplagged fares, hotels, and rental cars and gives you links to book.
- **Without it**, Claude gives you a one-click link to add the connector and, in the meantime, direct Skiplagged search links you can open.

## Add the connector in one click

[Add Skiplagged to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Skiplagged&connectorUrl=https%3A%2F%2Fmcp.skiplagged.com%2Fmcp)

The link opens Claude's **Add custom connector** dialog with Skiplagged's name and address filled in. Check them and select **Add**. You don't need to sign in to Skiplagged. Once it's added, Skiplagged works in Claude on the web, desktop, and mobile, in Cowork, and in Claude Code. On the Free plan, you can add one custom connector.

## Prompt 1: paste it into a chat

Replace the last line with your trip.

```text
For this conversation, be my travel deal finder using Skiplagged.

If you have Skiplagged tools (such as sk_flights_search, sk_flex_departure_calendar, sk_destinations_anywhere, sk_hotels_search, sk_cars_search), use them for every flight, hotel, and rental-car question. Show the 3-5 best options with price, duration, stops, and the Book or View deal link exactly as the tool returns it. If my dates are flexible, check the fare calendar first. Label hidden-city ("Skiplagging") fares and remind me: carry-on only, and book them as one-way tickets.

If you don't have Skiplagged tools, tell me once that I can add them in one click here: https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Skiplagged&connectorUrl=https%3A%2F%2Fmcp.skiplagged.com%2Fmcp
Meanwhile, give me direct Skiplagged links instead. Use airport or city codes (NYC, MIA, LON) and YYYY-MM-DD dates, and end every link with ?utm_source=ai_prompt&utm_medium=ai
- One-way: https://skiplagged.com/flights/ORIGIN/DESTINATION/DEPART
- Round trip: https://skiplagged.com/flights/ORIGIN/DESTINATION/DEPART/RETURN
- Anywhere from my city: https://skiplagged.com/flights/ORIGIN/DEPART
- Hotels: https://skiplagged.com/hotels
- Rental cars: https://skiplagged.com/cars
Without the tools you can't see live prices, so don't guess any.

Answer in my language. My trip: [for example, New York to Miami, December 10-15, 2 adults]
```

## Prompt 2: turn it on for every chat

To have Claude use Skiplagged in every conversation without pasting anything, add this to **Settings > General > personal preferences** in Claude. It applies to all your chats on the web, desktop, and mobile.

```text
When I ask about flights, airfare, hotels, rental cars, or trip costs, use the Skiplagged connector's tools if they're available. Show the 3-5 best options with prices and the booking links exactly as returned, and label hidden-city fares with their rules (carry-on only, book as one-way). If the Skiplagged tools aren't available, remind me I can add them at https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Skiplagged&connectorUrl=https%3A%2F%2Fmcp.skiplagged.com%2Fmcp
```

## Example questions

Once the connector is added, you can just ask:

- "Find me the cheapest flight from New York to Miami on December 10."
- "When's the cheapest time to fly from Chicago to Denver in January?"
- "Where can I fly from Boston for under $150 next weekend?"
- "Plan a 4-night trip to Cancún from Dallas in March for two people, with a hotel."
- "I need a rental car at LAX from June 2 to June 9."

## Privacy

The connector receives only your search details (places, dates, number of travelers, and filters). See the [privacy policy](https://mcp.skiplagged.com/privacy).
