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
Directory :  `~/ImmerseUI/Blueprints/BP_CharacterScreenDummy`
:::

# Customizable view BP_CharacterScreenDummy
when character screen is open `BP_CharacterScreenDummy` activate and connect to screen.
- `Change` event called by user interface with a `F_Item` parameter for make a distinction about content and subject.
- `BP_CharacterScreenDummy` can be change for custom structure and can be extended for new subject.
-  adding new subject also require an uptade in `E_EquipmentTag`.


---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Data/F_Item`
:::

## Structure

- Item `pawnable items like Gun,Helmet...`.
- MaterialInstance  `skins,color,texture etc...`
- Equipment Tag `subject in BP_CharacterScreenDummy`.

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
- Equipment Tag `subject in BP_CharacterScreenDummy`.
- Contents `list of F_CharacterSectionContent`.
