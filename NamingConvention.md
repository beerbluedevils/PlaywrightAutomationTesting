# DX1 Playwright Automation: Naming Conventions & Architecture Rules

This document serves as the official reference for naming conventions and architectural structure within the DX1 Playwright automation framework. It enforces a hybrid standard designed to ensure CI/CD pipeline stability (via web-native directory naming) while leveraging object-oriented file conventions suited for TypeScript, Java, and C# developers.

### Naming Convention

| Category | Rule | Example |
| :--- | :--- | :--- |
| **Directory Name** | `kebab-case` | `customers-and-leads/` |
| **Test File** | `kebab-case.spec.ts` | `trade-in-valuation.spec.ts` |
| **Page Object File** | `PascalCase.ts` | `CustomerSearchListPage.ts` |
| **Utility File** | `camelCase.ts` | `apiHelper.ts`, `dateUtils.ts` |
| **Variable / Function** | `camelCase` | `const inventoryPage`, `async clickLogin()` |
| **Constant / Env Var** | `UPPER_SNAKE_CASE` | `MAX_TIMEOUT`, `DX1_PASSWORD` |
| **Class** | `PascalCase` | `class LoginPage {}` |

---

### Updated Architectural Layout

Applying your specific adjustments, the folder tree now looks like this:

```text
root/
  ├── credentials/
  │   ├── test.env
  │   └── dev.env
  ├── global/
  │   ├── globalSetup.ts
  │   └── globalTeardown.ts
  ├── fixtures/
  │   ├── baseFixture.ts
  │   └── loginFixture.ts
  ├── pages/
  │   ├── login/
  │   │   └── LoginPage.ts
  │   ├── customers-and-leads/
  │   │   ├── customer-search/
  │   │   │   ├── CustomerSearchListPage.ts
  │   │   │   └── CustomerDetailPage.ts
  │   └── major-unit/
  │       └── inventory-list/
  │           ├── InventoryListPage.ts 
  │           └── UnitDetailPage.ts
  ├── utils/
  │   └── dataGenerator.ts
  └── tests/
      ├── sales-and-finance/
      │   └── create-new-deal.spec.ts
      └── inventory/
          └── receive-new-unit.spec.ts