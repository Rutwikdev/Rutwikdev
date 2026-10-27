## Task 15: Export and organize inventory reports

Task 15: Organize the inventory reports for my DB2 LUW to PostgreSQL schema migration.

I have been extracting metadata from my DB2 LUW schema using DBeaver.

Help me organize the exported inventory results into a consistent migration inventory folder.

Requirements:

1. Recommend clear filenames for table, column, primary key, foreign key, constraint, index, view, identity, sequence, trigger, routine, and dependency reports.
2. Propose a master migration tracker with these columns:
   - Source schema
   - Source object name
   - Object type
   - Target schema
   - Target object name
   - Inventory status
   - Conversion status
   - Validation status
   - Issue description
   - Evidence file
3. Explain how to track objects that do not exist in the source schema.
4. Inspect the existing project structure before suggesting file changes.
5. Do not assume file paths.
6. Do not overwrite or delete files.
7. Do not modify any database objects.

Show me the recommended folder structure and master tracker format. Stop after completing this task.

## Task 16: Review DB2 data types and PostgreSQL equivalents

Task 16: Analyze DB2 LUW data types and propose PostgreSQL equivalents.

Use the column inventory for my DB2 LUW schema [SCHEMA_NAME].

Identify:

1. DB2 data type
2. Proposed PostgreSQL data type
3. Length, precision, and scale considerations
4. Nullability and default-value considerations
5. Timestamp and time-zone risks
6. Character padding and string-comparison differences
7. Large-object mappings
8. Unsupported or ambiguous conversions
9. Recommended validation for each risky mapping

Requirements:

- Use the actual metadata provided; do not invent missing information.
- Clearly distinguish direct mappings from conversions requiring review.
- Do not generate or execute DDL yet.
- Present a mapping table and explain important risks.
- Stop after completing this task.

## Task 17: Identify SQL and identifier incompatibilities

Task 17: Identify DB2 LUW to PostgreSQL SQL and identifier incompatibilities.

Analyze the available source DDL and metadata for schema [SCHEMA_NAME].

Identify:

1. Reserved keywords used as object or column names
2. Quoted and case-sensitive identifiers
3. DB2-specific SQL syntax
4. DB2-specific functions and special registers
5. Default-value differences
6. Generated-column and identity behavior differences
7. Other features that may not work directly in PostgreSQL

Requirements:

- Do not rename objects automatically.
- Explain the proposed conversion for each incompatibility.
- Do not invent missing definitions.
- Do not execute or modify anything.
- Produce an exception list with recommended actions.
- Stop after completing this task.

## Task 18: Review constraints and indexes

Task 18: Analyze the constraint and index inventories for my DB2 LUW schema [SCHEMA_NAME].

Review:

1. Primary keys
2. Foreign keys
3. Unique constraints
4. Check constraints
5. Index definitions
6. Composite-column ordering
7. Cross-schema references
8. Missing referenced keys
9. Duplicate or conflicting object names
10. Dependency and conversion risks

Requirements:

- Use the verified inventory reports.
- Do not assume missing inventory data means an object is absent.
- Identify differences that require manual review.
- Do not generate or execute migration DDL.
- Produce a structured review report.
- Stop after completing this task.

## Task 19: Review views and routines

Task 19: Review DB2 LUW views, triggers, stored procedures, and functions for PostgreSQL compatibility.

Use the source definitions and dependency information available for schema [SCHEMA_NAME].

For each object, identify:

1. Object name and type
2. DB2-specific syntax or functions
3. Dependencies
4. Potential PostgreSQL incompatibilities
5. Required rewrite or conversion
6. Whether manual review is required

Requirements:

- Do not invent missing definitions.
- Classify each object as likely convertible, requiring rewrite, or requiring manual review.
- Explain the reason for each classification.
- Do not execute or modify any database objects.
- Produce a review report and stop.

## Task 20: Create conversion rules and an exception report

Task 20: Create a proposed DB2 LUW to PostgreSQL conversion rules file and exception report for schema [SCHEMA_NAME].

Use the verified source inventory and approved compatibility findings.

The conversion rules should record:

1. Source data type or feature
2. Target PostgreSQL equivalent
3. Conversion rule
4. Special handling required
5. Validation requirement

The exception report should record:

1. Source object
2. Object type
3. Conversion issue
4. Risk or impact
5. Proposed resolution
6. Decision required
7. Approval status

Requirements:

- Do not invent missing metadata.
- Mark uncertain conversions for manual review.
- Do not generate or execute the full migration DDL yet.
- Show the proposed formats and representative entries supported by available evidence.
- Stop after completing this task.

## Task 21: Convert one sample table

Task 21: Convert one DB2 LUW table definition into PostgreSQL-compatible DDL.

Use the source DDL and verified metadata I provide for one table in schema [SCHEMA_NAME].

Preserve:

1. Column order
2. Data types and appropriate lengths
3. Numeric precision and scale
4. Nullability
5. Default values
6. Identity behavior, where applicable
7. Approved table and column naming
8. Applicable constraints included in the approved scope

Requirements:

- Convert only one table.
- Explain every nontrivial conversion.
- Flag unsupported or ambiguous features.
- Do not invent missing definitions.
- Do not execute the generated DDL.
- Return the PostgreSQL DDL and a conversion checklist.
- Stop after completing this task.

## Task 22: Review the sample PostgreSQL DDL

Task 22: Review the proposed PostgreSQL DDL for my sample table against the DB2 LUW source definition and metadata.

Check:

1. Column names and order
2. Data types, lengths, precision, and scale
3. Nullability
4. Default values
5. Identity or generated-value behavior
6. Identifier case and reserved keywords
7. Constraints included in the approved scope
8. Compatibility risks

Requirements:

- Identify errors, omissions, and ambiguities.
- Provide corrected DDL only where supported by source evidence.
- Explain any changes.
- Do not execute the DDL or modify any database objects.
- Stop after completing this task.

## Task 23: Generate PostgreSQL DDL for all tables

Task 23: Generate PostgreSQL CREATE TABLE DDL for all base tables in my DB2 LUW schema [SCHEMA_NAME].

Use only the verified source inventory, approved conversion rules, and reviewed sample conversion.

Requirements:

1. Generate PostgreSQL-compatible table definitions.
2. Preserve column order and approved data type mappings.
3. Preserve nullability and default values.
4. Handle identity or generated values where applicable.
5. Use approved target schema and object-name mappings.
6. Identify dependencies and recommend a safe creation order.
7. Flag unsupported or uncertain conversions.
8. Do not silently omit any in-scope table.
9. Organize output by schema and table.
10. Do not execute the generated DDL.

First show the generation plan and one representative output file for review. Stop after completing this task.

## Task 24: Generate DDL for constraints and indexes

Task 24: Generate PostgreSQL DDL for the approved constraints and indexes in my DB2 LUW schema migration.

Use the verified source inventories and approved conversion rules.

Include, where applicable:

1. Primary keys
2. Foreign keys
3. Unique constraints
4. Check constraints
5. Indexes
6. Composite-column ordering
7. Cross-schema references

Requirements:

- Use the approved target schema and object-name mappings.
- Respect object dependencies.
- Identify unsupported or ambiguous features.
- Do not silently omit objects.
- Separate the proposed DDL by object type.
- Do not execute the DDL.
- Show the proposed output and stop after completing this task.

## Task 25: Convert remaining dependent objects

Task 25: Prepare PostgreSQL equivalents for the remaining dependent objects in my DB2 LUW schema migration.

Use verified source definitions, dependency information, and approved conversion rules.

Include applicable:

1. Views
2. Sequences
3. Triggers
4. Stored procedures
5. Functions
6. Other inventoried dependent objects within the approved migration scope

Requirements:

- Do not generate objects that are verified as absent from the source inventory.
- Respect dependencies and creation order.
- Identify DB2-specific syntax that requires rewriting.
- Flag unsupported or ambiguous conversions for manual review.
- Do not invent missing definitions.
- Do not execute any generated SQL.
- Present the proposed definitions and an exception report.
- Stop after completing this task.

At the end of Task 25, you should have the source inventory, compatibility analysis, approved conversion rules, a reviewed sample table, and proposed PostgreSQL DDL for the in-scope schema objects. The next phase is target preparation and controlled schema creation.
