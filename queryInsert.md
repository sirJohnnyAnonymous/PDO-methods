<?php require_once 'core/dbConfig.php'; ?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    //inserting and deleting from query
 <?php
  //additionally you can add a delete statement by using DELETE FROM and just type the id 
  $query = "INSERT INTO russia_grocery_item (ID, product_type, product_name,
  product_brand, date_added) VALUES(?,?,?,?,?)";

  $stmt = $pdo->prepare($query);
  
  $executeQuery = $stmt->execute(
      [101,"Milk","dbezerna","moscowMilk",'18/10/2026']
  );

  if ($executeQuery) {
    echo "query successful!";
  }
  else {
    echo "Query failed";
  }
 ?>
</body>
</html>
