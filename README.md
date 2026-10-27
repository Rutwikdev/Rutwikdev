## Task 1: Verify DB2 connection and database

I am using DBeaver connected to DB2 LUW. Help me verify the current connection and identify the connected database name and DB2 LUW version.

Provide read-only diagnostic SQL or DBeaver steps.

Do not assume the database name and schema name are the same. Do not modify anything.

Show the steps and stop.

## Task 2: Verify the target source schema

I have identified my DB2 LUW schema: [SCHEMA_NAME].

Write a read-only DB2 LUW diagnostic query to verify that this exact schema exists in the currently connected database.

Explain how to interpret zero rows. Use catalog columns supported by my DB2 LUW version.

Do not modify anything. Show only the SQL and a short explanation, then stop.

## Task 3: List all base tables

Write one read-only DB2 LUW SQL query to list all base tables in schema [SCHEMA_NAME] using appropriate system catalog views.

Return schema name, table name, and table type.

Exclude views and aliases. Sort by table name.

Do not modify anything. Show only the SQL and a short explanation, then stop.

## Task 4: Extract column metadata

Write one read-only DB2 LUW SQL query using SYSCAT.COLUMNS to extract column metadata for all tables in schema [SCHEMA_NAME].

Return:

1. Schema name
2. Table name
3. Column name
4. Column position
5. Data type
6. Column length
7. Numeric precision
8. Numeric scale
9. Nullable status
10. Default value
11. Identity column information, if available

Use catalog columns supported by my DB2 LUW version. Sort by table and column position.

Do not modify anything. Show only the SQL and a short explanation, then stop.

## Task 5: Extract primary keys

Write one read-only DB2 LUW SQL query using appropriate catalog views, such as SYSCAT.TABCONST and SYSCAT.KEYCOLUSE, to extract primary key metadata for schema [SCHEMA_NAME].

Return:

1. Schema name
2. Table name
3. Constraint name
4. Constraint type
5. Primary key column name
6. Column position within the primary key

Preserve the order of columns for composite primary keys.

Use supported catalog columns. Do not modify anything. Show only the SQL and a short explanation, then stop.

## Task 6: Extract foreign keys

Write a read-only DB2 LUW SQL query using appropriate catalog views, such as SYSCAT.REFERENCES and SYSCAT.KEYCOLUSE, to extract foreign keys defined on tables in schema [SCHEMA_NAME].

Return:

1. Source schema name
2. Source table name
3. Foreign key constraint name
4. Source column name
5. Referenced schema name
6. Referenced table name
7. Referenced column name
8. Column position in the foreign key
9. Referenced primary or unique key name, if available

Requirements:

- Filter foreign keys by the source schema.
- Preserve column order for composite foreign keys.
- Include references to tables in other schemas.
- Return one row per foreign key column.
- Sort by source table, constraint name, and column position.
- Use catalog columns supported by DB2 LUW.
- Do not modify any database objects.

Show only the SQL and a brief explanation. Stop after completing this task.

## Task 7: Extract unique and check constraints

Write a read-only DB2 LUW SQL query using appropriate catalog views to inventory unique constraints and check constraints defined on tables in schema [SCHEMA_NAME].

Return:

1. Schema name
2. Table name
3. Constraint name
4. Constraint type
5. Constraint columns, where applicable
6. Check constraint definition, where applicable

Requirements:

- Filter by my exact schema name.
- Include unique constraints and check constraints.
- Use the correct DB2 LUW catalog views and supported columns.
- Preserve column order for multi-column unique constraints.
- Do not modify any database objects.
- Show only the SQL and a brief explanation.
- Stop after completing this task.

## Task 8: Diagnose constraint query returning no rows

My DB2 LUW constraint inventory query returned zero rows or only some constraint types.

Help diagnose this with read-only SQL against the appropriate DB2 LUW catalog views.

Show constraint counts by type for schema [SCHEMA_NAME], explain the DB2 constraint type codes, and verify the schema filter and catalog-column names.

Do not modify anything. Show only the SQL and a short explanation, then stop.

## Task 9: Extract indexes

Write a read-only DB2 LUW SQL query using appropriate catalog views, such as SYSCAT.INDEXES and SYSCAT.INDEXCOLUSE, to extract indexes for tables in schema [SCHEMA_NAME].

Return:

1. Schema name
2. Table name
3. Index name
4. Uniqueness indicator
5. Indexed column names
6. Column order within the index
7. Sort direction, if available
8. Index type or other relevant properties, if available

Requirements:

- Filter by my exact schema name.
- Preserve the order of columns in composite indexes.
- Include indexes on all applicable tables in the schema.
- Use catalog columns supported by my DB2 LUW version.
- Do not modify any database objects.
- Show only the SQL and a brief explanation.
- Stop after this task.

## Task 10: Extract all view definitions

Task 10: Extract all view definitions from my DB2 LUW schema.

Write a read-only SQL query using the appropriate DB2 LUW system catalog views, such as SYSCAT.VIEWS.

Return:

1. Schema name
2. View name
3. View definition or SQL text, where available
4. Validity or other relevant status, if available in my DB2 version

Requirements:

- Filter by my exact schema name.
- Include all views belonging to this schema.
- Do not confuse views with base tables.
- Use catalog columns supported by my DB2 LUW version.
- If the full SQL definition is not available through the catalog query, explain how to retrieve it using DBeaver or DB2 tools.
- Do not modify any database objects.
- Show only the SQL and a brief explanation.
- Stop after completing this task.

## Task 11: Identify identity columns and sequences

Task 11: Inventory identity columns and sequences in my DB2 LUW schema.

Write read-only SQL queries using the appropriate DB2 LUW system catalog views.

Part A — Identity columns:

- Schema name
- Table name
- Column name
- Data type
- Identity generation mode
- Start value and increment, where available
- Minimum and maximum values, where available
- Cycle setting, where available

Part B — Sequences:

- Schema name
- Sequence name
- Data type
- Start value
- Increment
- Minimum and maximum values
- Cycle setting

Requirements:

- Filter by my exact schema name.
- Use catalog columns supported by my DB2 LUW version.
- If separate queries are required, provide them separately.
- Do not modify any database objects.
- Show only the SQL and a brief explanation.
- Stop after this task.

## Task 12: Extract triggers

Task 12: Inventory triggers in my DB2 LUW schema.

Write a read-only SQL query using the appropriate DB2 LUW system catalog view, such as SYSCAT.TRIGGERS.

Return:

1. Trigger schema
2. Trigger name
3. Table schema
4. Table name
5. Trigger event (INSERT, UPDATE, DELETE)
6. Trigger timing (BEFORE, AFTER, or INSTEAD OF, where applicable)
7. Trigger granularity
8. Trigger definition or SQL text, where available
9. Enabled or validity status, where available

Requirements:

- Filter by my exact schema name.
- Include triggers associated with tables in this schema, and explain how to identify triggers defined in other schemas that operate on these tables.
- Use catalog columns supported by my DB2 LUW version.
- Do not modify any database objects.
- Show only the SQL and a brief explanation.
- Stop after this task.

## Task 13: Extract stored procedures and functions

Task 13: Inventory stored procedures and functions in my DB2 LUW schema.

Write read-only SQL queries using the appropriate DB2 LUW system catalog views.

Return:

1. Schema name
2. Routine name
3. Routine type
4. Parameter metadata, where available
5. Language
6. Source or definition, where accessible

Requirements:

- Filter by my exact schema name.
- Use catalog columns supported by my DB2 LUW version.
- If the full definition is not available through the catalog query, explain how to retrieve it using DBeaver or DB2 tools.
- Do not modify any database objects.
- Show only the SQL and a brief explanation.
- Stop after this task.

## Task 14: Identify object dependencies

Task 14: Identify dependencies among objects in my DB2 LUW schema.

Write read-only SQL queries using appropriate DB2 LUW catalog views and supported dependency metadata.

Include tables, views, routines, triggers, and constraints where catalog information permits.

Return:

1. Dependent object schema and name
2. Referenced object schema and name
3. Dependency type
4. Source evidence

Requirements:

- Include dependencies within my schema and references to other schemas.
- Explain catalog limitations and where manual review is needed.
- Do not modify any database objects.
- Show only the SQL and a brief explanation.
- Stop after this task.
