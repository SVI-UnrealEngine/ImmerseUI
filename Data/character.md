---
label: Character
order: 88
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
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_CharacterScreen`
:::
# What is CharacterScreen?

Selector template can store customizable items/character  datas.

!!!
Data Load or Override : create a `text`,`float` structure array in SaveGame class and load `OnEnterLayer` for override/apply your changes.
!!!

Detail Panel > Default.

+++ Offset
vertical offset of generated element.
+++ Viewable Chapter Amount
constant value same time viewable section.
+++ DTCharacter Section
a datatable for customization items/skin etc...
+++

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_CharacterSection`
:::

# View Block WBPC_CharacterSection
view block generated on container `CharacterScreen`.
- take the count of opened amount and total amount of child items.
- randomly show last selected item.(changeable with save data).


---
:::sample
Directory :  `~/ImmerseUI/Blueprints/CharacterCustom/BP_CharacterScreenActor`
:::

# Customizable  BP_CharacterScreenActor
when character screen is open `BP_CharacterScreenActor` activate and connect to screen.
- `Change` event called by user interface with a `F_Item` parameter for make a distinction about content and subject.
-  adding new customizable target also require an uptade in `E_CharacterScreenTarget` (like pet,car,weapon).
-  adding new item for skeletal mesh and adding on socket also require an uptade in `E_EquipmentTag`.

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/CharacterCustom/CharacterScreenItem`
:::

# Base of item CharacterScreenItem
All character screen customizer item like material, component, can be created by using `CharacterScreenItem`
- logic must be written for each item
- override `ApplyItem` event for logics

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Data/F_Item`
:::

## Structure

- Item `spawnable items base on CharacterScreenItem `.

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Data/F_CharacterSectionContent`
:::

## Structure

- Title `content title main label`.
- Item `instance of F_Item`.
- IsLocked `Is content locked by default (when locked cannot reach concrete item/skin)`.
- Primer Detail `[OPTIONAL]`.
- Second Detail `[OPTIONAL]`.


---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Data/F_CharacterSection`
:::

## Structure

- Title `content title main label`.
- Target `screen target view in BP_CharacterScreenActor`.
- Contents `list of F_CharacterSectionContent`.
