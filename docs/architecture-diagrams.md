# Architecture Diagrams

## 1. System Context Diagram

The system context diagram shows the platform and its external actors.

```mermaid
flowchart TB
    User[User / Family]
    Platform[Intelligent Meal Planning Platform]
    LLM[LLM Service<br/>optional]

    User -->|Manages products, preferences, budget<br/>Views meal plans| Platform
    Platform -->|Requests recipe generation<br/>optional| LLM
    Platform -->|Returns meal plans and recipes| User
```

**Description:**  
The user interacts with the platform to manage available products, dietary preferences, and family budget, and to receive personalized meal plans and recipes. An optional external LLM service can be used by the recipe generation module.

---

## 2. Use Case Diagram

```mermaid
flowchart LR
    User((User))

    subgraph Platform
        UC1[Register / Login]
        UC2[Manage Profile]
        UC3[Manage Available Products]
        UC4[Manage Dietary Preferences]
        UC5[Manage Family Budget]
        UC6[Generate Meal Plan]
        UC7[View Meal Plan]
        UC8[View Recipe Details]
    end

    User --> UC1
    User --> UC2
    User --> UC3
    User --> UC4
    User --> UC5
    User --> UC6
    User --> UC7
    User --> UC8
```

**Main Use Cases:**
- Register / Login
- Manage Profile
- Manage Available Products
- Manage Dietary Preferences
- Manage Family Budget
- Generate Meal Plan
- View Meal Plan
- View Recipe Details

---

## 3. Component Diagram (Draft)

```mermaid
flowchart TB
    subgraph Frontend
        UI[User Interface<br/>React / Next.js]
    end

    subgraph Backend
        API[REST API]
        Auth[Authentication]
        UserService[User & Profile Service]
        ProductService[Product Inventory Service]
        PreferenceService[Preferences Service]
        BudgetService[Budget Service]
        MealPlanService[Meal Plan Service]
    end

    subgraph RecipeModule[Recipe Generation Module]
        RecipeEngine[Recipe Generation Engine]
        Optimizer[Constraint Optimizer]
    end

    subgraph Data
        DB[(PostgreSQL)]
    end

    UI --> API
    API --> Auth
    API --> UserService
    API --> ProductService
    API --> PreferenceService
    API --> BudgetService
    API --> MealPlanService

    MealPlanService --> RecipeEngine
    RecipeEngine --> Optimizer

    UserService --> DB
    ProductService --> DB
    PreferenceService --> DB
    BudgetService --> DB
    MealPlanService --> DB
    RecipeEngine --> DB
```

**Description:**  
- **Frontend** — user interface for managing data and viewing results.  
- **Backend** — REST API and services for users, products, preferences, budget, and meal planning.  
- **Recipe Generation Module** — responsible for generating recipes and meal plans under constraints (available products, preferences, budget).  
- **Database** — PostgreSQL stores users, products, preferences, budget, and recipes.

---

## Notes

- Diagrams are provided in Mermaid format and can be rendered in GitHub or exported to PNG/SVG.
- The Component Diagram is a draft and will be refined during implementation.
- All diagrams are consistent with the requirements defined in UMP-5.

---

**YouTrack:** UMP-6  
**Assignee:** Әли Рауан Мақсатұлы  
**Status:** Draft for pre-defense (October 2026)
