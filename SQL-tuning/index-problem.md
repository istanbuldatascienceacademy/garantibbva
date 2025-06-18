```
SELECT
    ind1.table_name,
    ind1.index_name AS parent_index,
    ind2.index_name AS redundant_index,
    ind1.column_list AS parent_columns,
    ind2.column_list AS redundant_columns
FROM (
    SELECT
        index_name,
        table_name,
        LISTAGG(column_name, ',') WITHIN GROUP (ORDER BY column_position) AS column_list
    FROM dba_ind_columns
    GROUP BY index_name, table_name
) ind1
JOIN (
    SELECT
        index_name,
        table_name,
        LISTAGG(column_name, ',') WITHIN GROUP (ORDER BY column_position) AS column_list
    FROM dba_ind_columns
    GROUP BY index_name, table_name
) ind2
ON ind1.table_name = ind2.table_name
   AND ind1.index_name <> ind2.index_name
   AND ind2.column_list LIKE ind1.column_list || '%'
ORDER BY ind1.table_name, ind1.index_name;
```

