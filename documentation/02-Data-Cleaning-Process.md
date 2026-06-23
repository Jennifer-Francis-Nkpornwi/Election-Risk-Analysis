# Data Cleaning Process

## Polling Unit Dataset and the Incident Report Dataset

The datasets were reviewed to identify and address data quality issues before analysis.

## Cleaning Activities Performed

### Standardized Text Fields

* Reviewed LGA and State names for consistency.
* Ensured naming conventions were uniform across datasets.

### Validated Vote Totals

The relationship below was checked:

`TotalVotesCast = PartyAVotes + PartyBVotes + PartyCVotes`

This validation helped identify potential data quality issues.

### Missing Values

* Missing values identified in vote columns were reviewed.
* Missing values were filled where supporting vote information existed and calculations could be verified.

### Data Quality Flag

A negative vote value was identified in the PartyCVotes column.

**Example:**

* Party A = 280
* Party B = 240
* Party C = -10
* Total Votes Cast = 510

Because vote counts cannot be negative, the record was flagged as a data quality issue and retained for transparency.

### Turnout Percentage

A new field was created:

`TurnoutPercentage = (TotalVotesCast ÷ RegisteredVoters) × 100`

This metric was used to evaluate voting participation levels across polling units.

### Anomaly Detection

AnomalyFlag was created using the following rules:

* Over-voting
* Perfect Turnout
* Zero Turnout
* Suspicious Low Turnout
* Normal

AnomalyIndicator was also created:

* 1 = Anomaly
* 0 = Normal

This allowed anomaly rates to be calculated at the LGA level.
