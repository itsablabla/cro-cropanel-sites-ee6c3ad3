# Mega-menu choice overload — dev spec
Site: allbirds.com · Priority 5 · Urgent · Effort: Medium (2-5 days)

## Problem
The mega-menu presents 20+ nav items with multiple subcategories, risking choice paralysis and decision fatigue for users.

## Evidence (from the live site)
> nav_items list contains 20 items including 'New Arrivals', 'Shop All', 'Bestsellers', 'LEATHER ALTERNATIVES', 'Men's Shoes', 'Sneakers', 'Slip Ons', 'Sandals', 'Active', 'All-Weather', 'Runner NZ', 'Cruiser', 'Tree Runner NZ', 'Socks', 'Men's Apparel', 'Women's Shoes', 'Trainers', 'Flats', 'Canvas Cruiser', 'Women's Apparel'.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Mega-menu with 20+ items, multiple subcategories, and repeated links across sections.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Simplify mega-menu to top 5-7 categories, use clear hierarchy, and reduce redundant links.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Simplify mega-menu to top 5-7 categories, use clear hierarchy, and reduce redundant links.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_mega_menu_choice_overload` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
