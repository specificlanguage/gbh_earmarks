## gbh_earmarks

This is a data science analysis workspace for the data me and my team used for 
analyzing earmarks handed out by Massachusetts from the American Rescue Plan Act (ARPA).

Most of the analysis, include the categorization based on keywords, is inside `earmarks_analysis.ipynb`, with a little housing tangent inside `housing_calcs.ipynb`.

Nearly all the raw data is inside the `data` folder, which contains:
- `earmarks.csv`: The original dataset of earmarks derived from https://www.mass.gov/service-details/arpa-bill-earmarks 
- `cities.csv`: A population dataset sourced from the 2020 census, which also contains demographic information from all Massachusetts towns (or in the census' case, county subdivisions).
- `acs_mortgage`, `acs_rent`, and `acs_rent_nb` are all American Community Survey information sheets, which are 5-year estimates of mortgage and rent data within Massachusetts. 
These contain the estimate of how much each people pay for rent or mortgages by their income.
- `amendments_house` and `amendments_senate` are a list of amendments towards the original ARPA bills in the Massachusetts House & Senate. These were very graciously sourced by students from Spark.
  - https://malegislature.gov/Bills/192/H4269 (final bill)
  - https://malegislature.gov/Bills/192/H4219/Amendments/House (House Bill)
  - https://malegislature.gov/Bills/192/S2564 (Senate Bill)
- `town_shapefile`s which were never used, but they're shapefiles representing each town in Massachusetts.

All of the analysis/transformed data was in the `out` folder, which contains `csv` and (mostly) `xlsx` versions of the following:
- `earmarks_categories`, which tagged each of the earmarks between the categories 
- `cities`, which is literally just cleaned cities from the form "Acushnet city, _ county, Massachusetts" -> "Acushnet". This was mostly helpful for the very unwieldy census location tags.
- `amendments_to_legis`, which mapped each one of the amendments of the bill to one of the earmarks in the original earmarks dataset, mostly helpful to see which legislator proposed each amendment.
- `money_per_project`, which said how many of each category was invested in each town. Each town has two columns for each category: one for the amount of earmarks allocated to that town, and then the money.
- `rent_fixed_towns` and `mortgage_fixed_towns` are the `acs_mortgage` and `acs_rent` files in `data`, but with towns fixed from `cities`.
