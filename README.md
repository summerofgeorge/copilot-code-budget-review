# Copilot Code budget review

Practice files for George Mount's Stringfest Analytics walkthrough, "What Excel users need to know about Copilot Code."

Use **Microsoft Copilot's Code tab**. Product availability and steps were checked November 5, 2026; this is a preview product.

## Follow along

1. Open `prompts.md` and send the planning prompt in a new Code session. It already includes the eight fictional rows, so uploading the CSV is optional.
2. Review the business rules, then send the build prompt. If Code asks about hosting, select the standalone file option.
3. Download the HTML file Code generates and open it in a browser. If file delivery fails, use the recovery prompts and Notepad steps in `prompts.md`. Check the values below before sending the final refinement prompt.
4. Open the revised HTML, repeat the checks, and export the Operations rows to CSV. Open that export in Excel.

`budget-actuals.csv` contains the same source data for checking in Excel. All amounts are fictional expenses in USD. No real company data or work-file connections are needed. GitHub is just the download location; cloning, commits, and a GitHub account are not required to do the exercise.

## Check your result

At $5,000 AND 10%: Freight and Temporary staff are Flagged. Supplies is below both thresholds ($4,999 / 9.998%); Audit fails the percentage test ($6,000 / 6%). Travel is Unbudgeted, with N/A percentage. Training is No spend, also N/A. Software is favorable; Events is on budget.

All departments: Budget $280,000; Actual $301,999; variance $21,999. Operations: Budget $150,000; Actual $165,999; variance $15,999.

Set the dollar threshold to $7,500, leaving percent at 10: no positive-budget row should be flagged. Travel stays Unbudgeted and totals stay the same. Reset to $5,000 and 10 before testing the Operations export: three source rows, the same totals, and the calculated columns.

In Excel, with the original CSV columns A:E, use `=E2-D2` for variance and `=IF(D2=0,"N/A",(E2-D2)/D2)` for variance percentage. Format numeric percentages as percentages. Compare underlying values, not rounded displays.

Build your own result from the prompts; generated layouts and wording will vary. This repository intentionally contains only the starting data, prompts, and this README.

[Copilot Code training for finance teams](https://stringfestanalytics.com/copilot-code-training/)
