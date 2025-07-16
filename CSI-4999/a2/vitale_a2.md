# Query 1
```sql
SELECT UPPER(string_field_0) AS string_field_0_upper FROM `my_dataset.input_table`;
```
![[Pasted image 20250715205910.png]]
# Query 2
```sql
SELECT * FROM `my_dataset.input_table` WHERE string_field_0 = 'wombo';
```
![[Pasted image 20250715210223.png]]
# Query 3
```sql
SELECT COUNT(*) FROM `my_dataset.input_table`;
```
![[Pasted image 20250715210534.png]]
# Query 4
```sql
SELECT
  a.string_field_0,
  a.string_field_1,
  b.col1,
  b.col2
FROM
  `csi-4999-466100`.my_dataset.input_table AS a
  JOIN
  `csi-4999-466100`.my_dataset.table_2 AS b
  ON a.string_field_0 = b.col1;
```
# Query 5
```sql
CREATE OR REPLACE TABLE `csi-4999-466100`.my_dataset.input_table AS
SELECT DISTINCT
  string_field_0,
  string_field_1,
  string_field_2
FROM
  `csi-4999-466100`.my_dataset.input_table;
```
# Query 6 & 7
```sql
CREATE OR REPLACE TABLE `csi-4999-466100`.my_dataset.data_for_normalization AS
SELECT
  *
FROM
  UNNEST(ARRAY[STRUCT('item_A' AS item_id, 10 AS value_field), STRUCT('item_B' AS item_id, 20 AS value_field),
  STRUCT('item_C' AS item_id, 30 AS value_field), STRUCT('item_D' AS item_id, 40 AS value_field), STRUCT('item_E' AS item_id,
    50 AS value_field)]);
CREATE OR REPLACE TABLE `csi-4999-466100`.my_dataset.normalized_data AS
WITH
  stats AS (
    SELECT
      MIN(value_field) AS min_val,
      MAX(value_field) AS max_val
    FROM
      `csi-4999-466100`.my_dataset.data_for_normalization
  )
SELECT
  t.item_id,
  t.value_field,
  (t.value_field - s.min_val) / (s.max_val - s.min_val) AS value_field_normalized
FROM
  `csi-4999-466100`.my_dataset.data_for_normalization AS t,
  stats AS s;
```
![[Pasted image 20250715212741.png]]
