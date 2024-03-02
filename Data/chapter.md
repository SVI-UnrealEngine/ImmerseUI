---
label: Chapter
order: 91
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
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_ChapterSelector`
:::
# What is ChapterSelector?

Selector template can store chapter/story/level datas.

!!!
Data Load or Override : create a `F_Chapter` array in SaveGame class and load `OnEnterLayer` for override/apply your changes.
!!!

Detail Panel > Default.

+++ Offset
generated element horizontal offsets.
+++ Viewable Chapter Amount.
constant value for same time viewable chapter.
+++

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_Chapter`
:::

# View Block WBPC_Chapter

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
Directory :  `~/ImmerseUI/Blueprints/Data/F_Chapter`
:::


## Structure

- Title `content title main label`.
- Brush  `content image`
- Sub Title `content sub label [OPTIONAL]`.
- Decleration 1 `[OPTIONAL]`.
- Decleration 2 `[OPTIONAL]`.
- Default Lock State `Is content locked by default (when locked cannot reach concrete level/map/item)`.

!!!
You must override `DefaultLockState` for updating states.(when a new level/map/mode unlocked).
!!!




