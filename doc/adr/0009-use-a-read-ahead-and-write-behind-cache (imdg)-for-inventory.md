# 9. Use a read ahead and write behind cache  (in memory data grid) for inventory

Date: 2020-11-03

## Status

Proposed

## Context

Inventory is fast moving. continous sales and replenishments will keep happening. Accurate picture of the inventory is key to a great customer experience. also there will be a burst of traffic during certain times of the day and we need to accomodate that without hurting inventory consistency

## Decision

Implement a read ahead and write behind cache for inventory - that can help speed up reads and increase throughput but also writes behind to a persistence

## Consequences

This means that we have either apache ignite or a hazelcast in memory fronting the persistence of inventory to enable both read ahead and write behind for increased throughput. this means that we have to pay in terms of hardware and also in terms of dev time as we need to have jobs that warm the cache, full load the cache in times of need (imdg failure) etc., and this is something we need to work with the business to understand if this is required at this stage or can this be done in subsequent phases as this involves cost and complexity
