# Data Merging and Modeling

## Challenge:

The polling unit dataset and incident report dataset needed to be combined using:
• State
• LGA
• ElectionYear

A key challenge was ensuring that LGA names matched correctly across both datasets.

## Approach:

Standardization: LGA names were standardized before merging to reduce matching errors.

Aggregating Incident Data:

The incident report dataset was grouped by:
• State
• LGA
• ElectionYear

The following metrics were generated:
• IncidentCount
• AvgSeverityScore

This prevented row duplication during the merge process.

## Merge Method

A Left Outer Join was performed.

This approach ensured:
• All polling unit records were retained.
• Incident information was added where available.

## Handling Missing Incident Data:

Where no incident records existed:
• SeverityScore was treated as zero.
• IncidentCount was treated as zero.

This prevented valid polling unit records from being excluded from analysis.
