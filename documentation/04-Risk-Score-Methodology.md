# Risk Score Methodology

## Objective:

The Risk Score was designed to estimate the likelihood of electoral irregularities within each LGA.

## Metrics Used:

### Anomaly Rate:

`AnomalyRate = (Total Anomalies ÷ Total Polling Units) × 100`

### Average Severity Score:

Average incident severity was calculated for each LGA.

Severity values were scaled to a 0–100 range.

### Incident Count:

Incident counts were aggregated by LGA and ElectionYear.

Values were scaled to a 0–100 range.

### Turnout Anomaly

An indicator was created to identify LGAs whose turnout patterns differed significantly from state averages.

## Risk Score Formula

Risk Score =
(AnomalyRate × 0.4)
+
(AvgSeverityScoreScaled × 0.3)
+
(IncidentCountScaled × 0.2)
+
(TurnoutAnomaly × 10)

## Weighting Rationale

Anomaly Rate received the highest weight because it directly reflects unusual voting behavior.

Severity Score and Incident Count provide evidence regarding the frequency and seriousness of reported election incidents.

Turnout Anomaly was included to capture unusual voter participation patterns that may warrant further investigation.
