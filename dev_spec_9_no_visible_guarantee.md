# No visible guarantee — dev spec
Site: allbirds.com · Priority 9 · Urgent · Effort: Medium (2-5 days)

## Problem
The product page lacks a visible guarantee or return policy near the price, so buyers may worry about fit and return hassle.

## Evidence (from the live site)
> Product page shows 'Anytime Ankle Sock' with 'Get Notified' CTA and 'Learn More' but no explicit guarantee or return policy text near the price.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: No guarantee or return policy visible in the product area.

## Required change
h1: Anytime Ankle Sock; cta: Get Notified; notes: Add a line under the price: 'Free 30-day returns' or '100% comfort guarantee' to reduce purchase risk.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a line under the price: 'Free 30-day returns' or '100% comfort guarantee' to reduce purchase risk.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_visible_guarantee` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
