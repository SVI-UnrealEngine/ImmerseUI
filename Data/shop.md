---
label: Shop
order: 90
icon: "/static/add.png"
---


<style>
    .sample {
        text-align: left;
        color: #000000;
        border-radius: 10px;
        background-color: #5f99f5;
        border: 1px solid #1956AF;
        padding-left: 10px;
        padding-top: 20px;
        margin-bottom: 20px;
    }
</style>



:::sample
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_ShopSelector`
:::
# What is ShopSelector?

Selector template can store item/badge/store element datas.

!!!
[OPTIONAL] Data Load or Override : create a `F_ShopItem` array in SaveGame class and load `OnEnterLayer` for override/apply your changes.
!!!

Detail Panel > Default.

+++ Offset
generated element horizontal offsets.
+++ Column Size
column size of contents.
+++ Row Size
row size of contents.
+++

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_ShopItem`
:::

# View Block WBPC_ShopItem

Detail Panel > Default.

+++ Hover Brush 
pointer hover state background change with this brush.
+++ UnHover Brush 
pointer unhover state background change with this brush.
+++ Material Parameter
Using for animate outline with parameters.
+++



---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Data/F_ShopItem`
:::

## Structure

- Title `content title main label`.
- Brush  `content image`
- Sub Title `content sub label [OPTIONAL]`.
- Decleration 1 `[OPTIONAL]`.
- Decleration 2 `[OPTIONAL]`.
- Default Lock State `Is content locked by default (when locked cannot reach concrete level/map/item)`.
- Price `product/item price`.

!!!
You must override `DefaultLockState` for updating states. when an item purchaseable one time you can add a boolean in this structure and also add a purchased background in `ShopItem` for open when purhacement completed.
!!!





