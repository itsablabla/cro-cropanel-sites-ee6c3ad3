# Hero CTA lacks urgency — dev spec
Site: allbirds.com · Priority 6 · Urgent · Effort: Medium (2-5 days)

## Problem
The hero section's CTAs 'SHOP MEN' and 'SHOP WOMEN' are generic and don't leverage the new collection or urgency, potentially reducing click-through.

## Evidence (from the live site)
> Hero copy: 'Wildly Comfortable. Super Natural.' with CTAs 'SHOP MEN' and 'SHOP WOMEN'. Body sample also mentions 'New Dasher NZ Collection' but it's not in the hero.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Hero lacks specific product or collection mention; CTAs are generic.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Shop the New Dasher NZ Collection; notes: Use a specific collection CTA to create urgency and relevance.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Use a specific collection CTA to create urgency and relevance.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_hero_cta_lacks_urgency` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
