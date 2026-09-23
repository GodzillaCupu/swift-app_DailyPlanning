# Stitch AI Prompts — Daily Planner

Prompt siap pakai untuk [Stitch](https://stitch.withgoogle.com). Urutan mengikuti `docs/APP_FLOW.md`. Style prompt dipakai duluan supaya semua screen berikutnya konsisten, lalu tiap screen di-generate satu-satu di project Stitch yang sama.

## 0. Style Prompt (jalankan pertama, jadi acuan tone visual)

```
Design system for an iOS 18 productivity app called "Daily Planner" that combines
a to-do list and a budget tracker in one app. Native iOS look and feel, following
Apple Human Interface Guidelines — SF Pro typography, standard iOS spacing and
corner radius, system colors with a calm, minimal aesthetic (not colorful/playful).
Support both light and dark mode. Primary accent color: a muted teal/green.
Use native iOS components: tab bar, navigation bar with large title, grouped
list/form style, sheet presentations for add/edit forms, SF Symbols for icons.
```

## 1. Main Hub (Tab Bar)

```
iOS app home screen with a bottom tab bar with 3 tabs: "Tasks" (checklist icon),
"Budget" (dollar/wallet icon), "Charts" (chart icon). Show the Tasks tab as
active/selected. Navigation bar with large title "Tasks" and a "+" button top right
and a settings gear icon top left.
```

## 2. Tasks Tab (List)

```
iOS to-do list screen, navigation large title "Tasks". Grouped list of tasks,
each row shows: checkbox/checkmark circle on the left, task title, small due-date
label in gray below the title, and a category color dot on the right. Include a
segmented control or filter chips at top for "All / Today / Completed". Empty
state design also needed: centered icon + "No tasks yet" text + "Add your first
task" button.
```

## 3. Add/Edit Task Sheet

```
iOS modal sheet (partial height, swipe-down to dismiss) titled "New Task" with a
form: text field for task title, a row for due date with a date picker, a row for
category selection (colored chips: Work, Personal, Health, etc.), a toggle for
"Remind me" with a time picker that appears when enabled. Cancel button top left,
Save button top right (disabled/gray until title is filled).
```

## 4. Task Detail

```
iOS detail screen for a single task, navigation title is the task name. Shows
due date, category badge, notes/description text block, and a large checkmark
button to mark complete. Edit button top right, delete option accessible via a
trailing swipe action or a menu (three-dot icon).
```

## 5. Budget Tab (List)

```
iOS budget tracker screen, navigation large title "Budget". Top section shows a
summary card: total spent this month, budget limit, and a horizontal progress
bar (green to red gradient as it approaches the limit). Below, a grouped list of
transactions, each row shows: category icon, transaction title, date, and amount
aligned right (red for expense, green for income).
```

## 6. Add/Edit Transaction Sheet

```
iOS modal sheet titled "New Transaction" with a form: segmented control for
"Expense / Income", large numeric amount input at the top center, text field for
title/note, row for category selection (colored chips), row for date picker.
Cancel top left, Save top right.
```

## 7. Charts Tab

```
iOS analytics screen, navigation large title "Charts". Two sections stacked
vertically: (1) "Spending by Category" — a donut/pie chart with a legend listing
category, color dot, and percentage; (2) "Task Completion Trend" — a simple bar
or line chart showing tasks completed per day over the last 7 days. Use native
iOS card containers with rounded corners and subtle shadow for each chart section.
```

## 8. Settings

```
iOS settings screen, navigation large title "Settings", grouped list style
(like native iOS Settings app) with sections: "Notifications" (toggle for task
reminders, toggle for budget alerts), "Appearance" (light/dark/system picker),
"About" (version number, link to GitHub).
```

## 9. Weather App — Current Weather Screen

```
Minimal iOS weather app main screen. Large city name at top, huge temperature
number below it, weather condition text and icon (sun/cloud/rain SF Symbol style),
row of small stats (humidity, wind, feels like). Background is a subtle gradient
matching the weather condition (blue for clear, gray for cloudy). Pull-to-refresh
and a small "change location" button top right.
```

## 10. Weather App — Home Screen Widget

```
iOS home screen widget (small size, 2x2 grid) for a weather app: city name,
weather icon, current temperature large, high/low temperature small below.
Clean minimal widget design matching iOS 18 widget style with subtle background
matching weather condition.
```

---

**Tips pemakaian:**
- Generate screen 0 (style) dulu di Stitch, baru screen 1–8 satu per satu di project yang sama supaya Stitch mempertahankan konsistensi style.
- Setelah hasil keluar, bandingkan ke `docs/APP_FLOW.md` — pastikan tiap transisi (list → detail → sheet) match dengan yang digenerate.
- Stitch bagus untuk *starting point* layout, tapi hasilnya sering butuh disesuaikan ke pola native iOS asli (spacing, safe area, dynamic type) saat implementasi SwiftUI — jangan copy pixel-perfect, jadikan referensi struktur & hierarchy.
