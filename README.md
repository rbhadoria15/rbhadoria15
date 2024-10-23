SELECT 
    "column",
    "default"
FROM 
    pg_table_def
WHERE 
    schemaname = 'your_schema_name' AND
    tablename = 'your_table_name';

