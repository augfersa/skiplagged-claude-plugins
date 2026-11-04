# Hidden-city ("Skiplagging") fares: what to tell the user

A hidden-city fare is a ticket to a farther city with a layover in the city the user actually wants. The user gets off at the layover. For example, someone who wants New York → Charlotte might book New York → Miami with a stop in Charlotte when that ticket is cheaper.

Whenever you recommend or list a hidden-city fare, tell the user these points in plain words:

1. **Carry-on only.** Checked bags are sent to the ticket's final destination, so the user shouldn't check a bag on a hidden-city itinerary.
2. **Book it as a one-way.** If the user skips a segment, the airline can cancel the rest of the itinerary, including a return flight on the same ticket. For a round trip, search each direction as its own one-way.
3. **Plans can change.** If the airline reroutes the flight (for example after a delay), the new route may not stop at the user's city.

Keep it to these three points unless the user asks for more. For questions about risk, the Skiplagged Guarantee, or other policies, call `sk_faq_search` and answer from the returned articles, with their links.

If any of these rules doesn't fit what the user needs (checked bags, a round trip on one ticket, a tight schedule), search again with `includeHiddenCity: false` and show standard fares instead.
