### Query Functions ###
  * filter (string $statement)
  * limit  (int $start, int $end)
  * order  (string $statement)
  * query  ()

### Setters/Getters ###
  * get    (string $field)
  * set    (string $filed, mixed $value)
  * save   (array $field=>$value)

### Helpers ###
  * count  ()
    * Returns the count of **all** entries in a database, not based on query

### Retrieve/Delete ###
  * fetch  (int $primary\_key)
  * delete (int $primary\_key)
    * Deleting an entry auto-commits

### Save to database ###
  * reindex()
    * migrate or fixes broken indices
  * commit ()
    * currently only saves/updates an entry to the database