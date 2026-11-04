# Skiplagged Travel

Find cheap flights, hotels, and rental cars with [Skiplagged](https://skiplagged.com) without leaving your conversation with Claude. This includes hidden-city ("Skiplagging") fares, which are often the lowest price on a route. You don't need a Skiplagged account or an API key.

## What it does

The plugin connects Claude to the Skiplagged travel search connector and adds skills that teach Claude how to use it well:

| Skill | What it's for |
| --- | --- |
| `find-flights` | One-way and round-trip flights, flexible-date price calendars, nonstop and airline filters, and hidden-city fares with clear guidance |
| `find-hotels` | Hotel deals by city and dates, sorted by discount, price, rating, or value, plus room-level details |
| `find-rental-cars` | Rental-car offers at an airport or city, including one-way rentals |
| `plan-trip` | A full trip with flights, a hotel, and a car, priced in one table |
| `explore-destinations` | The cheapest places to fly from your city when you're flexible about where to go |

Results include direct links to book on skiplagged.com. Claude can't book or pay for you.

## Use it

After you install the plugin, connect the **Skiplagged** connector from the plugin's **Connectors** tab on claude.ai. It doesn't ask you to sign in. In Claude Code, the connector loads automatically.

Then ask in your own words, for example:

- "Find me the cheapest flight from New York to Miami on December 10."
- "When's the cheapest time to fly from Chicago to Denver in January?"
- "Where can I fly from Boston for under $150 next weekend?"
- "Plan a 4-night trip to Cancún from Dallas in March for two people, with a hotel."
- "Find a hotel in Lisbon from May 3 to May 7 with a high guest rating."
- "I need a rental car at LAX from June 2 to June 9."

In Cowork and Claude Code you can also call a skill directly, for example `/skiplagged:find-flights`.

## Hidden-city fares

A hidden-city fare is a ticket to a farther city with a layover where you actually want to go, and you get off at the layover. When Claude shows one, it labels it and explains the rules: carry-on only, book it as a one-way, and the route can change if the airline reroutes the flight. To see only standard fares, just say so.

## Data

The plugin sends your search details (places, dates, number of travelers, cabin, filters, and currency) to the Skiplagged travel search connector at `https://mcp.skiplagged.com/mcp`. If you ask Claude to find your nearest airport, it can also send approximate location information that the Claude app provides. The plugin doesn't ask for or send your name, email, payment details, or account information, and the plugin itself stores nothing. Booking happens on skiplagged.com under its own terms.

The plugin contains only instructions (skills) and the connector's address. It runs no code on your computer.

- Privacy policy: https://mcp.skiplagged.com/privacy
- Connector documentation: https://skiplagged.github.io/mcp/
- Support: https://support.skiplagged.com or support@skiplagged.com

## License

MIT. See [LICENSE](LICENSE).
