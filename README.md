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
- Enum Update

  ```
  DB::statement("ALTER TABLE p_c_embassies MODIFY COLUMN apply_with ENUM('spouse', 'spouse and kid', 'kid', 'single', 'spouse and kid 2', 'spouse and kid 3', 'spouse and kid 4') NOT NULL");
  ```
  if not working
  ```
  DB::statement("UPDATE p_c_sponsors SET source = 'own' WHERE source IS NULL;");
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
- all php version
  ``` https://php.en.uptodown.com/windows/versions ```

