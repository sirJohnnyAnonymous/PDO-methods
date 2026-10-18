<?php require_once 'core/dbConfig.php'; ?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    //selecting everything from the table in a clean format
 <?php
 $stmt = $pdo->prepare("SELECT * FROM russia_grocery_item");
 if ($stmt->execute()) {
     echo "<pre>";
     print_r($stmt->fetchALL());
     echo "</pre>";
 }
 ?>
</body>
</html>
