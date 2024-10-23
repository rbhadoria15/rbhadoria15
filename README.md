SELECT 
    a.attname AS column_name,
    d.adsrc AS default_value
FROM 
    pg_attribute a
JOIN 
    pg_attrdef d ON a.attnum = d.adnum AND a.attrelid = d.adrelid
WHERE 
    a.attrelid = 'public.employees'::regclass
    AND a.attnum > 0
    AND NOT a.attisdropped;


SELECT *
FROM pg_table_def
WHERE schemaname = 'public' AND tablename = 'employees';
