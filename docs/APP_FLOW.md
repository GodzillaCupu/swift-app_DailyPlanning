# App Flow

Alur layar/navigasi, dianalogikan seperti scene flow di game — tiap layar = "scene", tiap tab = "hub area".

## Daily Planner

```mermaid
flowchart TD
    Launch([Launch]) --> Hub{{Main Hub: TabView}}

    Hub --> TasksTab[Tasks Tab]
    Hub --> BudgetTab[Budget Tab]
    Hub --> ChartsTab[Charts Tab]

    TasksTab --> TaskDetail[Task Detail]
    TasksTab -- "+" --> AddTask[/Add/Edit Task Sheet/]
    TaskDetail --> AddTask
    AddTask -- save/cancel --> TasksTab

    BudgetTab --> TxDetail[Transaction Detail]
    BudgetTab -- "+" --> AddTx[/Add/Edit Transaction Sheet/]
    TxDetail --> AddTx
    AddTx -- save/cancel --> BudgetTab

    ChartsTab --> SpendingChart[Spending by Category]
    ChartsTab --> CompletionChart[Task Completion Trend]

    Hub --> Settings[Settings]
    Settings --> NotifSettings[Notification Preferences]

    style Launch fill:#2e7d32,color:#fff
    style Hub fill:#3a5a7a,color:#fff
```

**Catatan navigasi:**
- `Main Hub` adalah `TabView` persisten — user selalu bisa balik ke salah satu tab tanpa reset state tab lain.
- `Add/Edit` sheet dipakai untuk create maupun update (form yang sama, judul berubah sesuai konteks).
- `Settings` diakses dari Hub (bukan salah satu tab utama) — analog "pause menu" di game, bisa diakses dari mana saja.

## Weather App (Side Quest)

Scope sengaja lebih simpel — cuma 1 alur utama, tanpa banyak percabangan.

```mermaid
flowchart TD
    Launch([Launch]) --> Current[Current Weather Screen]
    Current -- refresh/change location --> Current
    Widget[[Home Screen Widget]] -.reads same data source.-> Current

    style Launch fill:#2e7d32,color:#fff
    style Widget fill:#5a3a7a,color:#fff
```
