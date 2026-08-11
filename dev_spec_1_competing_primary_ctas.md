# Competing primary CTAs — dev spec
Site: allbirds.com · Priority 1 · Urgent · Effort: Medium (2-5 days)

## Problem
The hero presents two equally prominent CTAs (SHOP MEN and SHOP WOMEN) that split user intent and delay the path to a single product or category, reducing the clarity of the primary action.

## Evidence (from the live site)
> Hero section contains both 'SHOP MEN' and 'SHOP WOMEN' as primary CTAs, with no single dominant CTA; the page also shows 'Shop All' in the nav and 'Shop + -' in the cart drawer, creating multiple competing paths.
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN' and 'SHOP WOMEN' with no subheadline to clarify the brand's unique selling proposition.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Two equally weighted CTAs in the hero, no clear primary action.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP BESTSELLERS; notes: Replace the two CTAs with a single, high-intent CTA that leads to a curated bestseller collection, reducing choice overload and focusing the user on a single next step.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Replace the two CTAs with a single, high-intent CTA that leads to a curated bestseller collection, reducing choice overload and focusing the user on a single next step.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_primary_ctas` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
