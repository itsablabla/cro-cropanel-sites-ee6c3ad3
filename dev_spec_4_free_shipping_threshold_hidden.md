# Free shipping threshold hidden — dev spec
Site: allbirds.com · Priority 4 · Urgent · Effort: Low (0.5-2 days)

## Problem
The homepage promotes free shipping but only reveals the $100 threshold in the body copy, creating an expectation gap that may cause cart abandonment.

## Evidence (from the live site)
> Body sample: 'Free ground shipping on orders over $100' appears in the page body, but the hero CTA 'SHOP MEN' / 'SHOP WOMEN' does not mention the threshold.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Free shipping threshold is not visible near the hero CTA.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Add a subtext under the hero CTA: 'Free shipping on orders over $100' to set expectations early.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a subtext under the hero CTA: 'Free shipping on orders over $100' to set expectations early.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_free_shipping_threshold_hidden` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
