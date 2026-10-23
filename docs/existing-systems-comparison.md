# Existing Systems Comparison

## Introduction

This document compares existing meal planning and recipe applications with respect to the core requirements of the project: available products (pantry), dietary preferences, and family budget. Five real systems were selected for comparison. The goal is to identify what current solutions already provide and where the proposed platform can offer a more integrated approach.

## Selected Systems

1. **Eat This Much** — AI meal planner focused on calorie/macro targets, budget, and pantry awareness.
2. **PlateJoy** — Personalized meal planning with digital pantry and strong preference matching.
3. **Samsung Food (formerly Whisk)** — Recipe saving, meal planning, and grocery list generation.
4. **Cooklist** — Pantry tracking via store loyalty cards and purchase history, with recipe suggestions.
5. **SuperCook** — Recipe search based on ingredients the user already has at home.

## Comparison Criteria

| №   | Criterion                                     | Description                                                   |
| --- | --------------------------------------------- | ------------------------------------------------------------- |
| 1   | Available products / pantry tracking          | Ability to track and use products currently at home           |
| 2   | Dietary preferences                           | Support for diets, allergies, dislikes, cuisine preferences   |
| 3   | Family budget                                 | Consideration of budget when generating meal plans            |
| 4   | Meal plan generation                          | Automatic or semi-automatic weekly/daily meal plans           |
| 5   | Recipe suggestions from available ingredients | Ability to suggest recipes based on what the user already has |
| 6   | Grocery list                                  | Automatic generation of a shopping list                       |
| 7   | Family / multi-user support                   | Support for household size and shared preferences             |
| 8   | Platforms                                     | Mobile / web availability                                     |
| 9   | Pricing model                                 | Free tier, subscription, or one-time purchase                 |

## Comparison Table

| Criterion                          | Eat This Much                       | PlateJoy                      | Samsung Food         | Cooklist                            | SuperCook                  |
| ---------------------------------- | ----------------------------------- | ----------------------------- | -------------------- | ----------------------------------- | -------------------------- |
| Available products / pantry        | Partial (pantry-aware regeneration) | Yes (digital pantry)          | Limited              | Yes (via loyalty cards / purchases) | Yes (ingredient selection) |
| Dietary preferences                | Strong (diet, allergies, macros)    | Strong (detailed preferences) | Moderate             | Basic filters                       | Basic                      |
| Family budget                      | Yes                                 | Limited                       | No                   | Limited (price comparison)          | No                         |
| Meal plan generation               | Yes (automatic, goal-based)         | Yes (personalized weekly)     | Yes (calendar-based) | Partial                             | No (search only)           |
| Recipes from available ingredients | Partial                             | Yes                           | Limited              | Yes                                 | Yes (main feature)         |
| Grocery list                       | Yes (automatic)                     | Yes                           | Yes                  | Yes                                 | No                         |
| Family / multi-user                | Yes                                 | Yes                           | Limited              | Limited                             | No                         |
| Platforms                          | iOS, Android, Web                   | iOS, Android, Web             | iOS, Android, Web    | iOS, Android                        | iOS, Android, Web          |
| Pricing                            | Free + Premium (~$5/mo)             | Subscription                  | Free + Premium       | Subscription                        | Free                       |

## Analysis

**Eat This Much** is one of the strongest existing solutions for goal-based and budget-aware meal planning. It supports dietary preferences, household size, and has some pantry awareness. However, pantry tracking is not a primary feature, and the system is more focused on calorie/macro targets than on maximizing the use of products already available at home.

**PlateJoy** offers deep personalization and a digital pantry that allows the system to prioritize recipes using ingredients the user already has. It reduces grocery costs and food waste in practice. Budget optimization is less explicit than in Eat This Much.

**Samsung Food** is widely used for saving recipes and generating grocery lists. It has basic meal planning capabilities but does not strongly integrate available products or budget constraints into the planning process.

**Cooklist** stands out for automatic pantry population from grocery store loyalty cards and purchase history. It can suggest recipes based on what the user has bought. However, it is less focused on structured weekly meal planning and budget optimization.

**SuperCook** is specialized in finding recipes from ingredients the user already has. It is free and simple, but it does not generate multi-day meal plans, does not consider budget, and offers limited preference handling.

## Gap

None of the reviewed systems simultaneously and strongly optimizes for all three constraints that are central to the project:

- Products currently available at home,
- Dietary preferences,
- Family budget.

Some systems handle two of the three reasonably well (for example, Eat This Much — preferences + budget; PlateJoy — preferences + pantry; SuperCook — pantry). However, an integrated solution that treats all three as first-class constraints when generating meal plans and recipes is still missing in mainstream applications.

## Conclusion

Existing applications provide useful individual features such as meal plan generation, pantry tracking, preference filtering, and grocery list creation. Nevertheless, they do not fully address the combined problem of planning meals based on available products, user preferences, and family budget. This gap justifies the development of the proposed intelligent platform.

---

**YouTrack:** UMP-3  
**Assignee:** Хавал Мирас Болатханулы
