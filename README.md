# Magento Grouped Products, with an optional clickable link to the product page

This customization for <strong>Magento 2 grouped products</strong> changes the default layout to <strong>display the SKU and product name</strong>, replacing the typical product name and quantity field. It also adds functionality to <strong>display the SKU as a clickable link to the associated product page</strong>, but only if the grouped product belongs to specific categories.

In the example provided, the condition checks whether the parent product is in a designated category (e.g., ID 63). If true, the SKU will appear as a link; otherwise, it will be displayed as plain text:
```
$targetCategoryIds = [63]; // Add your category IDs here

```

This approach is helpful when you want to <strong>control which grouped product listings include links</strong>, based on category relevance.

## Note: 

If you prefer to add the link for all associated products regardless of category, simply remove the category condition and wrap the SKU in an <a> tag like this:
```
<a href="<?= $block->escapeUrl($_item->getProductUrl()) ?>">
    <?= $block->escapeHtml($_item->getSku()) ?>
</a>

```
This will ensure every SKU listed in the grouped product view links to the corresponding product page.

## Implementation:

This can be implemented by modifying the grouped.phtml template.

This example demonstrates how to display the SKU and product name for each associated product within a grouped product. 

#### This script has been tested and verified to work in Magento 2.3 and Magento 2.4.