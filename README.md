# Penny: Personal Expense Tracker

A Java-based project for smart personal finance management. This repository contains the working web version: a fast, private expense tracker that runs in any browser with no signup and no installation.

> Turn scattered, untracked spending into clear financial awareness.

## Table of contents

1. [Overview](#overview)
2. [Problem statement](#problem-statement)
3. [Objectives](#objectives)
4. [Features](#features)
5. [How to use the app](#how-to-use-the-app)
6. [Methodology](#methodology)
7. [Technology stack](#technology-stack)
8. [Getting started](#getting-started)
9. [Project structure](#project-structure)
10. [Data model](#data-model)
11. [Smart categorization rules](#smart-categorization-rules)
12. [Planned Java architecture](#planned-java-architecture)
13. [Testing checklist](#testing-checklist)
14. [Browser support](#browser-support)
15. [Privacy and data storage](#privacy-and-data-storage)
16. [Known limitations](#known-limitations)
17. [Troubleshooting](#troubleshooting)
18. [Roadmap](#roadmap)
19. [Expected outcome](#expected-outcome)
20. [Author](#author)

## Overview

Penny helps people record, categorize, and monitor their daily spending in one simple place. It shows how much has been spent this month, how much of the budget is left, and warns the user before and after a limit is crossed.

| Item | Details |
|------|---------|
| Project title | Personal Expense Tracker |
| App name | Penny |
| Project type | Software development project |
| Current version | Web app (HTML, CSS, JavaScript) |
| Planned version | Java application with Swing or JavaFX and a database |
| Target users | Students and young professionals |

**Live demo:** open the website link shown in the **About** section on the right side of this repository page.

## Problem statement

Most people lack a simple, personal way to track where their money goes. Manual notebooks are tedious, and many commercial finance apps are complex, paid, or collect unnecessary personal data.

This gap leads to:

- Overspending
- Missed budgets
- Poor long-term financial habits, especially among students and young professionals

The idea behind this project: you can't manage what you don't measure.

## Objectives

| No. | Objective | Description |
|-----|-----------|-------------|
| 1 | Simple expense logging | Record daily expenses with amount, category, date, and description |
| 2 | Smart categorization | Group spending into food, transport, bills, entertainment, and more |
| 3 | Insightful reports | Generate daily, weekly, and monthly spending summaries |
| 4 | Budget control | Let users set budget limits and get alerted before overspending |
| 5 | Easy data management | Support editing and deleting past records without hassle |
| 6 | User-friendly interface | Deliver a clean, easy experience for all users |

## Features

### Expense logging
- Add an expense with amount, date, note, and category
- Input validation: the amount must be greater than zero and a date is required
- Notes can be up to 60 characters

### Smart categorization
- The category is suggested automatically from keywords in the note, for example "lunch" is filed under Food
- You can always choose a category yourself
- Anything unrecognized is filed under Other

### Managing records
- Edit any expense and save the changes
- Delete any expense, with an **Undo** option right after
- Search by note or category
- Filter by category and by month

### Reports
- **Daily:** the last 7 days
- **Weekly:** the last 8 weeks (weeks start on Monday)
- **Monthly:** the last 6 months
- A bar chart for each period, with the current period highlighted
- A category breakdown showing where the money went

### Budget control
- A total monthly limit
- Optional limits for each category
- A ring on the Overview page showing how much budget is left
- Alerts when spending reaches 80% of a limit, and again when the limit is passed

### Experience
- Works on phones, tablets, and desktops
- Automatic dark mode that follows the device setting
- Currency choice: $, ₹, €, or £
- Keyboard-friendly, with visible focus outlines

## How to use the app

The app has four sections, shown as tabs at the top.

### 1. Overview
- The ring shows the money left this month, or the amount spent if no limit is set.
- Alerts appear beside the ring when a limit is close or exceeded.
- Use the **Add an expense** form to record spending. Type a note and Penny suggests a category.
- The **Recent** list shows your last five expenses with Edit and Delete buttons.

### 2. All expenses
- See every record, newest first.
- Use **Search**, **Category**, and **Month** to narrow the list.
- The line above the list shows the count and total of what is currently shown.

### 3. Reports
- Choose **Daily**, **Weekly**, or **Monthly**.
- Read the bar chart, then check **Where it went** for the category split.

### 4. Budget
- Enter a total monthly limit.
- Optionally add a limit for any category.
- Tap **Save budget**. Leave a field empty for no limit.

### Editing an expense
1. Tap **Edit** on any expense. The form opens with its details filled in.
2. Change what you need and tap **Save changes**.
3. Tap **Cancel** to leave without saving.

### Trying the app with sample data
When the list is empty, tap **load sample data** in the Recent card to fill the app with example expenses and a sample monthly budget.

## Methodology

The app follows a five-step flow.

| Step | Name | What happens |
|------|------|--------------|
| 1 | Input | The user enters an expense: amount, category, date, note |
| 2 | Validate | The system checks the data before saving |
| 3 | Store | The data is saved on the device |
| 4 | Process | Totals, category splits, and budget checks are calculated |
| 5 | Report | Summaries, charts, and budget alerts are shown |

Budget alerts trigger automatically whenever category or overall spending crosses a limit the user has set. This turns tracking into active financial guidance, not just record-keeping.

## Technology stack

### Current web version
| Layer | Technology |
|-------|------------|
| Structure | HTML5 |
| Styling | CSS3 (custom properties, grid, flexbox) |
| Logic | Vanilla JavaScript, no frameworks or libraries |
| Charts | Inline SVG drawn by the app |
| Storage | Browser localStorage |
| Font | Bricolage Grotesque from Google Fonts, with system fonts as a fallback |
| Hosting | GitHub Pages |

### Planned Java version
| Layer | Technology |
|-------|------------|
| Language | Core Java with OOP principles: classes, inheritance, encapsulation |
| Interface | Swing or JavaFX desktop GUI |
| Database | SQLite or MySQL through JDBC |
| Backup | CSV or text file handling |
| IDE | Eclipse or IntelliJ IDEA |
| Version control | Git and GitHub |

## Getting started

### Option 1: Use the website
Open the website link in the **About** section of this repository.

### Option 2: Run it on your computer
1. On this repository page, click the green **Code** button and download the project as a ZIP file.
2. Extract the ZIP file.
3. Double-click `index.html`. It opens in your default browser.

No build step, server, or installation is needed.

### Option 3: Clone with Git
1. Click the green **Code** button and copy the HTTPS address.
2. Run this in a terminal, pasting the address you copied:
   ```
   git clone <the-address-you-copied>
   ```
3. Open the new folder and double-click `index.html`.

### Hosting your own copy with GitHub Pages
1. Open the repository **Settings**.
2. Select **Pages** in the left menu.
3. Under **Build and deployment**, set the source to **Deploy from a branch**.
4. Choose the `main` branch and the `/ (root)` folder, then click **Save**.
5. Wait a minute or two. The site address appears at the top of the Pages screen.

## Project structure

```
penny-expense-tracker/
├── index.html     The complete app: layout, styles, and logic
└── README.md      Project documentation
```

Files such as `.gitignore` may also appear if they were added when the repository was created.

The app is a single file on purpose. It is easy to host, easy to read, and easy to move into the Java project later.

### Inside index.html

| Part | Purpose |
|------|---------|
| `<style>` block | Colors, layout, dark mode, and responsive rules |
| HTML sections | Overview, All expenses, Reports, and Budget screens |
| `<script>` block | Data handling, validation, categorization, budget alerts, charts, and rendering |

## Data model

### Expense
| Field | Type | Description |
|-------|------|-------------|
| id | Number | Unique identifier, created from the time of entry |
| amount | Number | Money spent, greater than zero |
| category | Text | One of the eight categories |
| date | Text | Date in YYYY-MM-DD format |
| note | Text | Short description, up to 60 characters |

### Budget
| Field | Type | Description |
|-------|------|-------------|
| total | Number | Monthly limit, 0 means no limit |
| cats | Object | Optional monthly limit for each category |

### Categories
Food, Transport, Study, Shopping, Bills, Fun, Health, Other

## Smart categorization rules

The app checks the note for these keywords. The first matching category is used.

| Category | Keywords |
|----------|----------|
| Food | lunch, dinner, coffee, pizza, grocer, snack, cafe, meal, breakfast, restaurant |
| Transport | bus, uber, taxi, fuel, petrol, metro, train, ride, cab |
| Study | book, course, tuition, pen, notebook, print, exam, fees |
| Shopping | shirt, shoes, amazon, clothes, gift, shop |
| Bills | rent, wifi, internet, electric, phone, recharge, subscription, bill |
| Fun | movie, game, netflix, concert, party, spotify |
| Health | doctor, medicine, pharmacy, gym, clinic |
| Other | Used when no keyword matches |

Matching works on parts of words, so "groceries" matches "grocer".

## Planned Java architecture

The Java version is designed around four modules and is the next stage of development.

```
Expense  →  ExpenseManager  →  Storage  →  UI
(model)     (logic)            (persistence)  (console / GUI)
```

| Class | Responsibility |
|-------|----------------|
| Expense | Model class holding id, amount, category, date, and note, with validation |
| ExpenseManager | Add, edit, delete, search, totals, category summaries, and budget checks |
| Storage | Save and load records through JDBC or file handling, plus CSV backup |
| UI | Swing or JavaFX screens for adding and viewing expenses and reports |

### Possible REST endpoints (if a web backend is added)
| Method | Path | Purpose |
|--------|------|---------|
| GET | /api/expenses | List expenses |
| POST | /api/expenses | Add an expense |
| PUT | /api/expenses/{id} | Edit an expense |
| DELETE | /api/expenses/{id} | Delete an expense |
| GET | /api/budget | Read budget limits |
| PUT | /api/budget | Save budget limits |
| GET | /api/reports?period=weekly | Summary for a period |

## Testing checklist

Use this list to check the app by hand.

| No. | Test | Expected result |
|-----|------|-----------------|
| 1 | Add an expense with a valid amount | It appears in Recent and in All expenses |
| 2 | Submit with an empty or zero amount | An error message asks for an amount greater than zero |
| 3 | Type "lunch" in the note and leave the category on Auto | The expense is filed under Food |
| 4 | Edit an expense and save | The changes show in the lists |
| 5 | Delete an expense | It disappears, and Undo brings it back |
| 6 | Set a total limit and spend 80% of it | A warning alert appears |
| 7 | Spend past the limit | An over-limit alert appears and the ring turns red |
| 8 | Open Reports and switch between Daily, Weekly, Monthly | The chart and category split update |
| 9 | Search, then filter by category and month | Only matching expenses are listed |
| 10 | Change the currency | All amounts show the new symbol |
| 11 | Refresh the page | All data is still there |
| 12 | Resize the window to phone width | The layout stays readable, with no sideways scrolling |

## Browser support

Works in current versions of Chrome, Edge, Firefox, Safari, and mobile browsers. Private or incognito windows may not keep saved data after they are closed.

## Privacy and data storage

- Your expenses and budgets are stored only in your own browser, using localStorage.
- No expense data is sent to any server, and no account is needed.
- The only outside request is for the web font from Google Fonts. If it cannot load, the app uses your system font.
- Clearing your browser's site data deletes your expenses.

## Known limitations

- Data does not sync between devices or browsers.
- Data is lost if the browser's site data is cleared.
- There is no CSV export in this version yet.
- There is no login, so everyone using the same browser sees the same data.
- Report charts cover fixed ranges: 7 days, 8 weeks, and 6 months.

## Troubleshooting

| Problem | What to try |
|---------|-------------|
| My data disappeared | Check that you are using the same browser and not a private window. Site data may have been cleared. |
| The live site shows a 404 error | Make sure the file is named exactly `index.html` and that GitHub Pages is turned on. Wait a few minutes after enabling it. |
| The page shows old content after an update | Refresh with Ctrl + Shift + R (Cmd + Shift + R on Mac). |
| The category was not suggested | The note has no known keyword. Pick a category yourself. |
| No alert appears | Check that a limit is saved under Budget and that the spending is in the current month. |
| The font looks different | The Google Font did not load, so a system font is used. The app works the same. |

## Roadmap

- [x] Expense logging with validation
- [x] Keyword-based category suggestions
- [x] Edit and delete with Undo
- [x] Search and filters
- [x] Daily, weekly, and monthly reports
- [x] Budget limits with alerts
- [x] Responsive layout and dark mode
- [x] Problem statement, architecture, and class design
- [ ] Java classes: Expense, ExpenseManager, Storage, UI
- [ ] Database storage with JDBC
- [ ] CSV export and backup
- [ ] Recurring expenses
- [ ] User accounts and login
- [ ] Cloud sync
- [ ] Mobile app

## Expected outcome

A fully functional personal expense tracker that lets users record, categorize, and monitor spending.

| Outcome | Meaning |
|---------|---------|
| Accurate tracking | Every expense is logged, categorized, and searchable |
| Better budgeting | Real-time alerts keep spending within limits |
| Clear reports | Instant monthly and category-wise summaries |
| Scalable design | Ready to extend with cloud sync and a mobile app |

## Author

| | |
|---|---|
| Name | Santhosh B |
| Roll number | 711525BEE054 |
| Role | Solo Developer |
| Project | Personal Expense Tracker |
| Focus areas | Java, OOP, file and database handling, GUI |

This project was created for academic purposes as part of a software development course.
