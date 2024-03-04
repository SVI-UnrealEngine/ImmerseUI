---
label: Chapter Update
order: 91
icon: "/static/setup.png"
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
# How Update Chapters?

!!!
Data Updates : create a `F_Chapter` array in SaveGame class and use `UpdateChapter` for override/apply your changes.
!!!

# Structure
- Title (`KEY for find chapter`)
- PlayTime (`[OPTIONAL] if is empty doesnt update`)
- LastSaveTime (`[OPTIONAL] if is empty doesnt update`)
- BlockedState (`[OPTIONAL] if is false level is unlocked`)


!!!
Unlocking Chapter/Level/Map :`PlayTime` and `LastSaveTime` must leaved empty and set `BlockedState` to `false`.
!!!

