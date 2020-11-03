# 7. Payment is done in realtime

Date: 2020-11-02

## Status

Accepted

## Context

Payment is taken upfront before the order is confirmed. 


## Decision

Payment is authorised in realtime through a synchronous call to the payment gateway and based on the response either the order is confirmed or if the payement is declined, User is asked to use another payment method

## Consequences

This makes sure that we take in orders for which payment is confirmed. This means that the onus is on us to deliver and if for whatever reason we couldnt deliver, we have to make sure we refund immediately rather than the standard 3-5 days (which will cause customer dissatisfaction). The advantage is that we avoid cases where there isnt any money on the card at the time of fulfillment. This seems an accepted trade-off at the moment.
