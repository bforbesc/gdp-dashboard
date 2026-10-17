# 📊 GDP Dashboard

> **Learning case study** · 📊 Data transformation · Data visualization · Web apps
>
> An experiment preserved for teaching. You can learn from the explanation, sample, and code even if the original app no longer runs.

[📚 Learning hub](https://github.com/bforbesc/Data-AI-with-Forbes) · [🧭 Beginner guide](https://github.com/bforbesc/Data-AI-with-Forbes/blob/main/START_HERE.md) · [🌐 Build and deploy a data app](https://github.com/bforbesc/Data-AI-with-Forbes/tree/main/templates/streamlit-starter)

## The idea before the tools

**How can a table become a chart that another person can explore?**

**CSV table → reshape and filter → chart and controls → interpretation**

This is a study of an approach, rather than a recommendation to adopt an old app. First explain what happens in each step; only then look at the library or framework that implements it.

| Tool in this project | What it does in the example |
|---|---|
| **Pandas** | Reads the table, reshapes year columns into rows, and filters observations. |
| **Streamlit** | Adds selectors, charts, and a page people can open in a browser. |

**Choose countries and years, and see how the story changes. No coding needed to explore it.**

This is a small Streamlit dashboard for exploring the size of economies over time. GDP means **gross domestic product**: the value of goods and services produced in an economy over a period. A dashboard lets you explore a question through charts and simple controls.

This project is part of [Data & AI with Forbes](https://github.com/bforbesc/Data-AI-with-Forbes), my home base for learning content and experiments. It adapts a Streamlit dashboard template and is kept as a historical teaching reference.

## What it does, and why

The app reads a table, lets you select countries and dates, draws a line chart, and compares the values at the start and end of your chosen period. It shows how a small amount of code can make a large table easier to explore—and how the choices behind a chart affect its meaning.

The bundled World Bank data covers **1960–2022**, uses **current US dollars**, and contains missing values. It is a historical snapshot, not live data. The country-code selector also contains regional aggregates, so use the named country codes below for the first activity.

## Start here: no coding

Open the [shared Streamlit GDP template demo](https://gdp-dashboard-template.streamlit.app/), or use this repository's app if your teacher runs it. The shared demo is an upstream example, not a verified deployment of this exact code; its data and controls may change. If it is unavailable, use the worksheet below with your teacher.

1. Find **Which countries would you like to view?** Remove the default selections and choose `PRT` (Portugal) and `ESP` (Spain).
2. Set **Which years are you interested in?** to 2000–2022.
3. Look at **GDP over time**. Which line is higher? Does that mean a typical person earns more?
4. Change the start year to 2010. Compare the endpoint cards below the chart. Write one sentence about what changed and one about what you cannot conclude.

You should see two lines and two country cards when using this repository's bundled data. A card's value is shown in billions of US dollars (`B`). Its `x` comparison means **end value divided by start value**: `2x` means twice the starting value, not 2% growth.

## A small worksheet: can the starting year change the story?

These are **fictional** figures for practice, in billions of current US dollars. They are not part of the World Bank dataset.

| Economy | 2000 | 2010 | 2022 |
|---|---:|---:|---:|
| A | 100 | 200 | 300 |
| B | 80 | 100 | 240 |

1. Which economy is larger in 2022?
2. Which grew by a larger multiple from 2000 to 2022?
3. Which grew by a larger multiple from 2010 to 2022?
4. What information is missing if you want to compare living standards?

<details>
<summary>Check your reasoning</summary>

A is larger in 2022: 300 versus 240. From 2000, both end at **3 times** their starting value. From 2010, A reaches **1.5 times** and B **2.4 times**. You would need population information for a per-person comparison, and should consider prices, exchange rates, and other measures of well-being. Total GDP alone does not answer that question.

</details>

## For teachers

Allow about 15 minutes. Ask students to predict before moving a control, then explain why the same dataset can support different comparisons. A blank value is missing information, not a zero. Current-dollar GDP changes also reflect prices and exchange rates; this app is not an inflation-adjusted growth calculator.

## Optional: run your own copy

Students exploring the demo do not need these steps. A teacher or someone familiar with Python can run the project locally:

1. On GitHub, choose **Code → Download ZIP**, extract it, and open a terminal in that folder.
2. With Python installed, create a separate environment and install the dependencies:

```bash
python -m venv .venv
```

Activate it on macOS/Linux with `source .venv/bin/activate`, or in Windows PowerShell with `.venv\Scripts\Activate.ps1`. Then run:

```bash
python -m pip install -r requirements.txt
python -m streamlit run streamlit_app.py
```

Open the local address Streamlit prints. Stop the app with **Ctrl+C** in the terminal. If Python is available as `python3` on your machine, use that to create the environment.

## Optional: look inside the code

In [streamlit_app.py](streamlit_app.py), `get_gdp_data` loads and reshapes the table. The slider and country selector collect your choices, the filter selects matching observations, and `st.line_chart` draws them. Start by finding one visible label in the code; you do not need to understand the whole file.

## Credits and reuse

Based on the [Streamlit GDP dashboard template](https://github.com/streamlit/gdp-dashboard-template), using bundled data attributed to [World Bank Open Data](https://data.worldbank.org/). The existing [Apache-2.0 license](LICENSE) is preserved. Dataset terms are separate from the code license. For a question about this project, [open an issue](https://github.com/bforbesc/gdp-dashboard/issues).
