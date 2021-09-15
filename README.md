# Analytics Engineer Challenge

## About XCLAIM
XCLAIM's core product is a 2-sided marketplace for buyers (hedge funds, banks, and some individual investors) and sellers (creditors) of claims (unpaid invoices) in a chapter 11 US-based bankruptcy. 

## Things You Should Know

### negotiations.csv
- id
- created_at
- buyer_entity_id
- claims

### negotiation_events.csv
- id
- created_at
- negotiation_id (same as the negotiation.id)
- legal_entity_id
- action

### Notes
- You can *assume* the negotiation event with the highest ID is the most recent.
- `buyer_entity_id` and `legal_entity_id` are from the same `legal_entities` table. If there is a `buyer_entity_id` that is the same as a `legal_entity_id` it is the same `legal_entity`. For example, id 882833, is a buyer.
- The first negotiation event in a negotiation .
- Seller actions/events are any event not made by the initial `buyer_entity_id` and may for the purposes of conversion, include only: offer, accept, and decline. Both buyers and sellers can have offer, accept, and decline events, but only a buyer can have the first offer even on a negotiation.
- It may be helpful to create a new list/table of valid buyers using the ids in `negotiation.buyer_entity_id` to understand when a `negotiation_event.legal_entity_id` is a buyer or seller.
- If there is no `negotiation_event.legal_entity_id` assume it is a `cancel` action.
- Warning: this data represents real world data and may have some inconsistencies.

## Your Task
Please dedicate no more than four hours to this challenge. Clone this repository, commit your code to your clone, and send a link Stuart, stuart@x-claim.com, a link to your repository when you are done. be sure include screenshots of the visualizations in your submission.

### Create Visualizations
1. Number of buyers (y) with an offer per month (x).
2. Number of unique claims with an offer (y) per month (x).

### Answer Questions
3. What percent of total negotiations have a seller action/event? What SQL statement(s) did you use?
4. Does seller conversion change based on receiving an offer from more than one buyer (`buyer_entity_id`)? What evidence can you provide to support your answer? What other data would you need to support/prove your assumptions?
5. What would a more normalized model for our data look like? Draw it out.

### For In-Person Discussion
6. How would you segment our data and/or customers?
7. How can you explain the rate (uneven) of negotiation events?
