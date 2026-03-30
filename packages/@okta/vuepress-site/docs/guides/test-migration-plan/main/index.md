---
title: Test and validate your migration
---

Testing and validating your migration plan is essential to ensure a successful transition to Okta. This guide covers the critical steps of data validation, testing, and rollback planning to help you identify and address issues before deploying your migration to production.

## Review and clean your data

Extract the user data from the source (or sources) into an intermediate staging area. Then you need to clean up that data so that it's consistent and contains only valid information. Careful review of the data in each field also helps avoid errors when migrating to Okta.

For example, verify that the data meets any constraint requirements:

* Data type and length
* Required fields are present
* Unique fields don't have duplicates

If you discover any issues, use a consistent strategy to remedy for every issue that includes:

* Capturing/recording each type of issue
* Logging each occurrence
* Counting occurrences and total number of issues
* Devising remediation and implementation steps
* Assigning and tracking remediation tasks

## Test your migration plan

Once you have a clean set of data, you can create a realistic set of test data that can be used to test your migration method. Testing uncovers issues with your data or the migration method so that issues can be addressed before going to production.

### Create a test plan

When creating a test plan, it's important to prepare the following:

* Data that was at the "tail end" of a process or calculation. This allows you to see right away if problems occurred in upstream processes.
* Any externally facing data.
* Data that is under regulation/privacy standards.
* Any data that kicks off significant revenue/productivity impacting processes downstream.

### Create test data

Create test data sets that keep these points in mind:

* Create multiple batches of test data so that you have a varied set of conditions to test against.
* Plan more loads as significant configuration and development changes are made.
* Plan progressively larger loads for performance indicators.

### Run your tests

Finally, when running your tests, ensure you execute all test cases and capture failed test cases in a defect log with details. For example:

* Use case number
* Issue description
* Test status
* Ticket status
* Priority
* Error category: AD, Okta, HR, or other specifics to your environment
* Notes/proposed resolution

> **Note:** It can be helpful to output errors in a format that can be the input for another run.

## Create a rollback plan

Identify users to roll back by assigning them to an Okta group that identifies the source. Do the users exist in Okta? If so, an export of the current user data, or a valid data source is needed.

Data migration rollback is for users only. Other items (for example, application assignment) should have their own plan. Isolate these other items by temporarily disabling those features during data migration.

## Next steps

With your testing and validation plan in place, you're ready to move on to implementation. Choose the migration method that best fits your needs:

* [Bulk migration with credentials](/docs/guides/migrate-to-okta-bulk/)
* [Import Users with Inline Password Hooks](/docs/guides/migrate-to-okta-password-hooks/)
