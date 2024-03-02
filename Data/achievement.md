---
label: Achievement
order: 89
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
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_Achievements`
:::
# What is Achievements?

Selector template can store achievements/milestone element datas.

!!!
Data Load or Override : create a `text`,`float` structure array in SaveGame class and load `OnEnterLayer` for override/apply your changes.
!!!

Detail Panel > Default.

+++ Column Size
column size of contents.
+++

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Widgets/Components/WBPC_AchievementItem | WBPC_AchievementUniformGrid`
:::

# View Block WBPC_AchievementItem
view block generated on container `WBPC_AchievementUniformGrid`.
- On completed background image pulled in the container widget.

# View Block WBPC_AchievementUniformGrid
generate all view block `WBPC_AchievementItem` and give some random success percentage.
- with some title and percentage variable create a save game data for override this percentage amount.

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Data/F_Achievement`
:::

## Structure

- Title `content title main label`.
- Sub Title `content sub label [OPTIONAL]`.






