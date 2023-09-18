<?php
ini_set('display_errors', 1);

use Magento\Framework\App\Bootstrap;

include('./app/bootstrap.php');

$bootstrap = Bootstrap::create(BP, $_SERVER);

$objectManager = $bootstrap->getObjectManager();

$state = $objectManager->get('Magento\Framework\App\State');
$state->setAreaCode('frontend');
$storeManager = $objectManager->get('\Magento\Store\Model\StoreManagerInterface');
$eavSetupFactory = $objectManager->get('\Magento\Eav\Setup\EavSetupFactory');
$attributeFactory = $objectManager->get('\Magento\Catalog\Model\ResourceModel\Eav\Attribute');
$store = $storeManager->getStore();
$store_id = $store->getId();

$objectManager = \Magento\Framework\App\ObjectManager::getInstance();
$productCollection = $objectManager->create('Magento\Reports\Model\ResourceModel\Report\Collection\Factory'); 
$collection = $productCollection->create('Magento\Sales\Model\ResourceModel\Report\Bestsellers\Collection'); 

$collection->setPeriod('month');
//$collection->setPeriod('year');
//$collection->setPeriod('day');
//echo "<pre>";print_r($collection);
foreach ($collection as $item) {
    echo "<pre>Data====";print_r($item->getData());
}
?>
