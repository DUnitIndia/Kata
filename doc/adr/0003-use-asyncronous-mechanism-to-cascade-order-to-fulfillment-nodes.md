# 3. Use Asyncronous Mechanism to cascade order to fulfillment nodes

Date: 2020-11-01

## Status

Accepted

## Context

Order flow to fulfillment nodes is through an asynchronous mechanism, an Order Topic. Orders are confirmed by the order module and sent to the fulfillment through a topic

## Decision

Making this flow asynchronous will benefit the order taking process as we dont want any failures here impacting the customer buying experience. we are decoupling the ordering from fulfillment here.

## Consequences

Any failures in downstream will NOT impact the customer buying. the order info can be fetched by multiple systems that are interested in the data rather than a point to point integation. Also the blast radius of one failure downstream is contained downstream. The flip side is that the listeners of the Topic for fulfillment have to always be up and respond (we will have monitoring for that anywhich ways) and there would be some minor latency between placing the order and getting the info onto the fridge. this would be in order of a few hundred ms (typilcally within 500 ms). This is deemed acceptable for the benefits this decision provides
