# Tech Employees' Donations To The Clinton and Trump Campaigns

This repository contains data and code supporting the BuzzFeed News article, "[Clinton Receives Thirty Times As Much Tech Cash As Trump](https://buzzfeed.com/hamzashaban/tech-donates-thirty-times-as-much-to-clinton)," published October 27, 2016.

## Data

The contributions used in this analysis come from Federal Election Commission filings submitted by Hillary Clinton and Donald Trump's principal campaign committees:

| Committee Name                      | Committee ID |
|-------------------------------------|--------------|
| HILLARY FOR AMERICA                 | C00575795    |
| DONALD J. TRUMP FOR PRESIDENT, INC. | C00580100    |

In *Schedule A, Line 17A* of those filings, the committees list all itemized contributions. (Committees are required to itemized contributions from any person who has given the campaign $200 or more during the 2015–16 election cycle.) In *Schedule A, Line 18*, the committees list transfers from other authorized committees, including the alloted portions of individual contributions to joint-fundraising committees (e.g., Trump Make America Great Again Committee). More details, including the computer scripts used to obtain the filings from the ProPublica Campaign Finance API and the FEC, can be [found here](https://github.com/BuzzFeedNews/presidential-campaign-contributions).

As with any broad analysis of campaign contributions, there's some imprecision involved. For example, some donors may not have correctly identified their employers. Additionally, campaigns are not required to “itemize” contributions from a donor until that donor has contributed $200 or more. And this analysis does not incorporate refunds to donors; in the FEC data, those reimbursements do not identify the payee’s employer.

## Analysis

The analysis was conducted in the Python programming language, and can be [found here](notebooks/tech-employee-contributions.ipynb).

__Company-by-company contribution totals__ for the 20 companies can be [found here](output/tech-employer-totals.csv). That spreadsheet has two numeric columns:

- `itemized_contributions` counts only the itemized contributions listing the employer.
- `sum_max_agg` tries to infer the total (including non-itemized contributions), based on the maximum `contribution_aggregate` field for each first-name/last-name/employer combination. This approach isn't foolproof but should, generally, provide an upper-bound estimate for contributions.

Individual __itemized donations__ from employees at those 20 tech companies can be [found here](output/tech-contributions.csv).

The __raw employer names__ included in the employer-name groups can be [found here](output/raw-employer-names.csv).

A rough assessment of the __employer names associated with the most money contributed__ to each campaign can be found [here](output/top-employers-clinton.csv) (Clinton) and [here] (output/top-employers-trump.csv) (Trump). For more detail regarding those lists, please see the bottom of the [analysis notebook](notebooks/tech-employee-contributions.ipynb).

## Feedback

Contact Jeremy Singer-Vine at jeremy.singer-vine@buzzfeed.com.

Looking for more from BuzzFeed News? [Click here for a list of our open-sourced projects, data, and code.](https://github.com/BuzzFeedNews/everything)

