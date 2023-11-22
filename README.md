=== Database Error==
- DB 1055 error (access violation) solution: 
  ```
    DB::statement("SET sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));");
  ```


=== Migration===
- Single table rollback
  ```
    php artisan migrate:rollback  --path=/database/migrations/2023_11_21_042309_create_applications_table.php
  ```


=== Array functionality ===
- 2D Array search for specific key
  ```
    array_search($key_value, array_column($your_2d_array, 'key_name'));
  ```
- 2D Array search for key range
  ```
     array_search(true, array_map(function ($array) use ($value) {
          return $marks['key1'] <= $value && $marks['key2'] >= $value;
     }, $marks));
  ```
