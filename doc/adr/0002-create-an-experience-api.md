# 2. Create an Experience API

Date: 2020-11-01

## Status

Accepted

## Context

Business has plans to onboad digital and website. it also has a mechanism to sell through smart fridges which themselves can function as a selling channel. with the advent of multi sensory selling, its imperative that a few more channels like Voice (Alexa or Google home) and chat based selling is only a few quarters away. Experiences keep changing and we have AR/VR coming into mainstream. 

## Decision

To enable experiece /channel agnostic commerce, we propose to have an experice layer which will feed on to different experiences like mobile, web, voice, chat and AR/VR. This layer will be on top of the process layer and will exclusively serve the experience. This decouples the process layer to evolve independent of the experience and also if a new experiene is to be onboarded, the effort is less as it just an extension

## Consequences


Adding the new layer will help in abstracting the internal processes and provide a single point of integation for the experience channels. This will mean that to onboard a new experience, it would be a simple effort to integrate with this layer.

The cost of this is that we have to develop this and this will involve upfront dev and test costs. also there would be minor latency issues - in the order of few ms, as it goes through a layer of transformation/aggregation but thats an acceptable costs compared to the longterm benefits