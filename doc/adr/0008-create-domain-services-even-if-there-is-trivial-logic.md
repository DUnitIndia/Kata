# 8. Create domain services even if there is trivial logic

Date: 2020-11-02

## Status

Proposed

## Context

There are quite a few domain services that dont have complex logic today and can be clubbed

## Decision

Do not club the services and keep them seperate even if the logic inside is trivial today. it makes extensibility easy as we can evolve each service independently of each other without any impact as we grow

## Consequences

Obviously, writing these many domain services today is expensive (atleast the boiler plate + the trivial logic) but this is offset by the fact that as we grow we can evolve independently each domain and the cost we pay at that time is less

We may have to work with the business to see if this exercise is worth the effort in terms of cost to develop and the time to market. 
