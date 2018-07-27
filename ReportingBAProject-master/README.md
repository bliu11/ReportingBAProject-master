# Reporting Business Analyst Project

This project is meant to demonstrate several of the skills we are looking for in the Data Team for the Reporting Business Analyst position based on a real problem we have needed to solve in the past. Some requirements are left intentionally vague so that we can see your architecting and problem solving skills, and to allow you some creative freedom. That being said, do not hesitate to ask us questions about the project.

## Project Description

Create a formatted spreadsheet report using Pandas and OpenPyXL for the fake insurance company Insurio Inc using the provided CSV files as input.
The Finance department of Insurio Inc needs a new report to track the changes in the transactional premium. They are interested in a report that shows the YTD changes in premium by policy with the following columns:

Column | Description | Formatting
-- | -- | --
Policy Number | The Policy Number is a sequential number assigned to every policy when bound | No specific formatting needed
Named Insured | The insured’s full name. A policy can have multiple named insureds, in those cases we want to show all of them separated by comma | No specific formatting needed
Effective Date | This is the date when a coverage or insurance contract goes into effect or starts | d/m/YYYY (eg. 1/8/2018)
Transaction Type | The type of transaction associated with the revision: New, Endorsement, Canceled, Reinstated | No specific formatting needed
Policy Fee | Fees associated with a policy | Number with no decimals
Change in Premium | The difference in premium among previous revision and the current one | Two decimals, thousands separated by comma

The Policy Fees need to be removed from flat cancellations. These are policy cancellation transactions where the cancel date is less or equal than the Effective Date.


## Formatting

- Two header rows with the name of the company and the month or time period that the report corresponds to (See image below)
- Underlined and bold headers (See image below)
- Add spreadsheet filters to the headers (See image below)

<img src="https://github.com/IntuitiveWebSolutions/ReportingBAProject/blob/master/format_example.png?raw=true"/>

## Available data

- policies.csv
- revisions.csv
- fees.csv
- policyholders.csv

## Terminology

### Policy

A policy can have multiple status:
- Active The policy may be in effect, depending upon if the associated revision is committed or not
- Canceled The policy is not in effect
- Cancellation Pending The policy is currently in effect but will not be as of a future date
- Expired The policy was non-renewed and is not in effect

###  Revisions

A revision is the foundation of a policy and tracks the changes to a policy over time, including written premium. The following revision states indicate whether the revision's information is in effect:
- Committed The data associated with the revision is in effect and reportable
- Open and Pending The data associated with the revision is in progress and, therefore, is neither in effect nor reportable
- Archived The data associated with the revision was at one time in effect and is reportable

### Fee

Any item with a dollar amount to be reported as a fee:
- Policy Fee
- New York State Fire Fee

## Deliverables

Put all of your relevant code and documentation in a git repository. We prefer GitHub, but as long as it is web accessible, you can put it up wherever you have an account. Please make sure you include some instructions of how to run or test manually your report.

## Bonus Points

If you have extra time and really want to impress us, here are a few suggestions:
- Define and add possible test scenarios and tests to make sure that if there are changes in code results are the same in the future
- Add some charts or useful insights to your spreadsheet report using Pandas or any charting library
