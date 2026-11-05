# Copilot Code budget review prompts

Tested in Microsoft Copilot Code on November 5, 2026. Use these in the Code tab, not an Excel Copilot chat.

## 1. Plan

```text
Help me plan a small budget-versus-actuals review app for an FP&A analyst. Do not build it yet.

Use only this fictional expense data. All amounts are USD and every row is an expense:
Period,Department,Account,Budget,Actual
2026-10,Operations,Freight,50000,56000
2026-10,Operations,Temporary staff,50000,55000
2026-10,Operations,Supplies,50000,54999
2026-10,Finance,Audit,100000,106000
2026-10,Finance,Software,20000,18000
2026-10,Sales,Travel,0,2000
2026-10,Sales,Events,10000,10000
2026-10,Finance,Training,0,0

The app should calculate Actual minus Budget. Positive variance is unfavorable. For positive budgets, variance percent is variance divided by Budget. Flag an expense only when unfavorable variance is at least $5,000 AND at least 10%, using unrounded values. Show zero-budget rows with positive actuals separately as Unbudgeted; their percentage is N/A. Zero budget and zero actual is No spend, also N/A.

I want totals, a department filter, adjustable dollar and percentage thresholds, a clear review table, and a CSV export of the filtered rows including the calculated columns and review status. Totals should follow the department filter, but changing thresholds must not change the underlying Budget or Actual amounts.

Keep this a self-contained practice app with no external services, work-file connections, sign-in, or publishing. Restate the rules, propose the smallest useful layout, and tell me any assumptions before building.
```

Read the plan. If asked about hosting, choose a standalone file. Confirm the listed assumptions only if they match the article: row-level thresholds, all selected rows included in totals, whole-percent input, and zero-budget exceptions kept separate.

## 2. Build

```text
Build the agreed standalone app now as a single HTML file I can download and open in a browser. Embed the eight sample rows and all code in the file; use no external services or libraries. Keep the business rules unchanged. Use a white background, readable text, clear labels, and a red accent for unfavorable items. Include text statuses as well as color. Show variance percentages to three decimal places so Supplies does not look identical to Temporary staff. Give me a download link when it is ready.
```

## 3. Explain the result

```text
Add a column called "Why this status" to both tables and the CSV export. Explain each row's result in plain English using its actual dollar variance, unrounded percentage, and the current thresholds. For zero-budget rows, explain why the percentage is N/A. Update the explanation when I change a threshold. Keep every calculation, source amount, filter, and existing status rule unchanged. Give me the revised standalone HTML file.
```

