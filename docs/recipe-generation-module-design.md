# Recipe Generation Module — Design

## 1. Purpose

The Recipe Generation Module is responsible for generating personalized meal plans and recipes based on three main constraints:

- Available products (pantry / inventory)
- Dietary preferences
- Family budget

The module is developed by Мұхтарұлы Нұрасыл and integrates with the server-side via API.

## 2. Inputs

| Input | Description | Source |
|-------|-------------|--------|
| Available products | List of products currently at home (name, quantity) | Product Inventory Service |
| Dietary preferences | Restrictions, allergies, preferred cuisines, disliked ingredients | Preferences Service |
| Family budget | Maximum amount the user is willing to spend | Budget Service |
| Planning period | Number of days or meals (e.g. 3 days, 7 days) | User request |
| Household size | Number of people | User profile |

## 3. Outputs

| Output | Description |
|--------|-------------|
| Meal plan | List of meals for the requested period |
| Recipes | Full recipes (name, ingredients, steps, estimated cost) |
| Missing products | Products that are needed but not available (optional) |
| Estimated total cost | Approximate cost of the generated plan |

## 4. High-Level Approach

The module uses a **hybrid approach**:

1. **Filtering** — exclude recipes that violate dietary preferences or require unavailable products beyond an acceptable threshold.
2. **Scoring / Optimization** — rank or select recipes that maximize the use of available products and stay within the budget.
3. **Generation / Adaptation** (optional) — use an LLM or rule-based generation to adapt recipes or create variations when needed.

### Processing Steps

```
Available products + Preferences + Budget
        ↓
Filter candidate recipes
        ↓
Score recipes (product match, cost, preferences)
        ↓
Select / optimize meal plan
        ↓
Return meal plan + recipes + estimated cost
```

## 5. Constraint Handling

| Constraint | How it is handled |
|------------|-------------------|
| Available products | Prefer recipes that use products already in stock; minimize missing ingredients |
| Dietary preferences | Hard filter — recipes violating restrictions are excluded |
| Family budget | Soft or hard constraint — total estimated cost should not exceed the budget |
| Variety | Avoid repeating the same recipe too often within the planning period |

## 6. Integration with Server-Side

- The module is called by the **Meal Plan Service** via internal API or service call.
- It receives structured data (products, preferences, budget) from the backend.
- It returns a structured meal plan that the backend stores and sends to the frontend.
- The module does not directly access the database; data is provided by the server-side services.

## 7. Responsibilities

| Component | Responsibility |
|-----------|----------------|
| Recipe Generation Module (Нұрасыл) | Filtering, scoring, optimization, and generation of meal plans and recipes |
| Server-side (Рауан) | Providing input data, calling the module, storing results, exposing API to frontend |
| Frontend (Мирас) | Displaying the generated meal plan and recipes to the user |

## 8. Future Extensions

- Integration with an external LLM for recipe adaptation
- More advanced optimization (e.g. minimizing food waste)
- Support for multi-day variety and leftover reuse

---

**YouTrack:** UMP-8  
**Assignee:** Мұхтарұлы Нұрасыл  
**Status:** Draft for pre-defense (October 2026)
