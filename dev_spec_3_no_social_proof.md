# No social proof — dev spec
Site: allbirds.com · Priority 3 · Urgent · Effort: Medium (2-5 days)

## Problem
The hero lacks any social proof, so first-time visitors may doubt the comfort claim and hesitate to click through.

## Evidence (from the live site)
> Hero H1: 'Wildly Comfortable. Super Natural.' with CTAs 'SHOP MEN' and 'SHOP WOMEN' but no review count, rating, or testimonial visible.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: No social proof in hero section.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Add a line under the CTAs: 'Rated 4.6/5 from 150,000+ reviews' or a small trust badge strip.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a line under the CTAs: 'Rated 4.6/5 from 150,000+ reviews' or a small trust badge strip.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_social_proof` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
