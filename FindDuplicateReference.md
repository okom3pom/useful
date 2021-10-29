```
include_once('config/config.inc.php');
include_once('init.php');

$sql = "SELECT `id_product` FROM `ps_product` WHERE `active` = 1 ";

$products = Db::getInstance()->executeS($sql);

foreach ($products as $product) {
    $sql2 = "SELECT `reference`, COUNT(reference) as qty
            FROM `ps_product_attribute`
            WHERE `id_product` = " . (int)$product['id_product'] . "
            GROUP BY `reference`
            HAVING COUNT(reference) > 1
		";

    $duplicates = Db::getInstance()->executeS($sql2);

    foreach ($duplicates as $duplicate) {
        echo $duplicate['reference'] . ' --> ' . $duplicate['qty'] . ' <br>';
    }
}
```
