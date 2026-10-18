//DEMONSTRATING AN SQL QUERY’S RESULT SET IS RENDERED ON AN HTML TABLE
<?php require_once 'core/dbConfig.php'; ?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
 <?php
// 1. Run the SQL query to get the data
$stmt = $pdo->prepare("SELECT * FROM russia_grocery_item");
if ($stmt->execute()) {
    $groceryItems = $stmt->fetchAll();
}
?>

<!-- 2. Render that result set inside an HTML table -->
<table>
    <tr>
        <th>ID</th>
        <th>Product Type</th>
        <th>Product Name</th>
        <th>Product Brand</th>
        <th>Date Added</th>
    </tr>

    <?php foreach ($groceryItems as $item) { ?>
        <tr>
            <td><?php echo htmlspecialchars($item['ID']); ?></td>
            <td><?php echo htmlspecialchars($item['product_type']); ?></td>
            <td><?php echo htmlspecialchars($item['product_name']); ?></td>
            <td><?php echo htmlspecialchars($item['product_brand']); ?></td>
            <td><?php echo htmlspecialchars($item['date_added']); ?></td>
        </tr>
    <?php } ?>
</table>
</body>
</html>
