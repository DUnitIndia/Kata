# 4. Use realtime inventory check to confirm inventory availability at nodes

Date: 2020-11-01

## Status

Accepted

## Context

Inventory is a key domain entity that keeps moving as and when sales happens and as and when the nodes receive replenishments. It is a key value whose accuracy determines if we are over-selling or under-selling our inventory. Overselling causes customer dissatisfaction and underselling causes blocked inventory, shrikages, expiry of items (as this is a food item) and overall decrease in sales and increased inventory carrying costs

## Decision

Realtime checks on inventory during purchases enables us to see if the selectd node (say an apartment building where i want to pick) has the required item and then allow it and if not, show it as out of stock

## Consequences

getting consistency on inventory is a hard problem as various forces are at play. Still, minmising the time duration within which inventory is inconsistent (potentially) is what we have to solve for. to that effect, making a realtime inv call to the inventory system and then accepting an order potentially could save us from customer dissatisfaction and in the process increase sales. 

Maybe in a few edge cases, we may end up not selling a few/overselling, and we estimate this to be say one in 10,000 that too on potential hot sku's but that is an acceptable trade-off.

