# Architecture Diagrams

## 1. System Context Diagram

The diagram shows the platform and the main external actors.

```mermaid
flowchart LR
    User[User]
    Platform[Meal Planning Platform]
    LLM[LLM Service]

    User -->|Manage products, preferences and budget| Platform
    User -->|View meal plans and recipes| Platform
    Platform -->|Generate or adapt recipes| LLM
```

The user manages available products, dietary preferences and family budget through the platform and receives personalized meal plans. An external LLM service may be used by the recipe generation module.

---

## 2. Use Case Diagram

```mermaid
flowchart TB
    User((User))

    subgraph Account
        UC1[Register / Login]
        UC2[Manage profile]
    end

    subgraph Inventory and Preferences
        UC3[Manage available products]
        UC4[Manage dietary preferences]
        UC5[Manage family budget]
    end

    subgraph Meal Planning
        UC6[Generate meal plan]
        UC7[View meal plan]
        UC8[View recipe details]
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

Main use cases cover account management, inventory and preferences, and meal plan generation and viewing.

---

## 3. Component Diagram

```mermaid
flowchart TB
    subgraph Frontend
        UI[Web / Mobile Client]
    end

    subgraph Backend
        API[REST API]
        Auth[Authentication]
        UserSvc[User Service]
        ProductSvc[Product Service]
        PrefSvc[Preferences Service]
        BudgetSvc[Budget Service]
        MealSvc[Meal Plan Service]
    end

    subgraph RecipeModule[Recipe Generation Module]
        Engine[Recipe Engine]
        Optimizer[Constraint Optimizer]
    end

    DB[(PostgreSQL)]

    UI --> API
    API --> Auth
    API --> UserSvc
    API --> ProductSvc
    API --> PrefSvc
    API --> BudgetSvc
    API --> MealSvc
    MealSvc --> Engine
    Engine --> Optimizer

    UserSvc --> DB
    ProductSvc --> DB
    PrefSvc --> DB
    BudgetSvc --> DB
    MealSvc --> DB
    Engine --> DB
```

The frontend communicates with the backend through a REST API. The Meal Plan Service uses the Recipe Generation Module to produce plans that satisfy available products, preferences and budget constraints. All persistent data is stored in PostgreSQL.

---

## Notes

Diagrams are written in Mermaid and rendered directly in GitHub. The component diagram is a draft and will be refined during implementation.

---

