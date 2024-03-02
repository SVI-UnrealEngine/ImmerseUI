---
label: Start
order: 90
icon: "/static/finish.png"
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

---
:::sample
Directory :  `~/ImmerseUI/Blueprints/Widgets/WBP_UserInterface`
:::
# Overview
- `WBP_UserInterface` = Control the main ui and setup `WidgetLayer`'s with presets data.
- `WidgetLayer` = Base of all WidgetSwitcher childs, except of main menu.
- `BP_WidgetWorker` = Level object for create Main Widget and animate element using Timeline.
- `BP_MenuPawn` = Menu level pawn for call menu controll (OPTIONAL), change location and render `BP_ScreenBG`.
- `BP_ScreenBG` = Level object 3D screens connectable to widget.

---
## BP_WidgetWorker
Level object for create Widget and using Timeline with UI.
- Structure
    - AnnouncementBoxSetUp `main menu announcement box widget setups and bindings`.
    - AnnouncementBoxSlides `slide announcement box widget with Timeline`.
    - MoveOnTilmeLine_SlideHorizontal `move Widgets with transform ref and parameter on Timeline Horizontal`.
    - MoveOnTilmeLine_SlideVertical `move Widgets with transform ref and parameter on Timeline Vertical`.

---
## BP_MenuPawn
Menu level pawn for controll/render 3D stuffs
- Structure
    - SetUp Mapping and GameMode.
    - CineCamera `Menu render camera overrided PP and view setting by ScreenBg cinecamera`.
    - OpenScreen `Close last used ScreenBG and open target screen`.
    - Menu Controls Call `Can connected to WBP_UserInterface Control Comment Section`.
    - OpenLoadingScreen.

---
## BP_ScreenBG
Level object 3D screens connectable to widget.
- Structure
    - CineCamera `get custom view and PP for per screen `.
    - BG `Plane for render texture`.
    - MoveBackground `Abbility of move 3D plane with pointer delta`.
    - OnOpen `On Open Screen Overridable Event`.
    - OnClose `On Close Screen Overridable Event`.

---
## WidgetLayer
Base of all WidgetSwitcher childs, except of main menu.
 - Structure
    - bIsInitialized `is data generated`.
    - MainLayer `WBP_UserInterface Referance`.
    - OnEnterLayer `On Enter Layer Overridable Event`.
    - OnExitLayer `On Exit Layer Overridable Event`.

---

## WBP_UserInterface

Detail Panel > Default

+++ MenuButton Enter Speed 
piano style enter motion speed.
+++ Use Exit Control
overrided from `CurrentWidgetLayer`.
+++ Sounds
sounds added for demonstration, add some new sound and pull in the target `WidgetLayer` with using `GetMainLayer.SoundLabel`.
+++

Detail Panel > Data Table 

+++ Data Table 
contain all generative datas and initialize to `WidgetSwitcher` childs `WidgetLayer`.
+++

Detail Panel > Widget Layer

+++ Widget Layer 
list of widget layer setting, samely indexed with Widget Switcher child.
- Title
    - Back To Main Menu `when we don't need, leave just empty the back MM block will close automatically [OPTIONEL]`.
- Connected Screen
    - 3D world connected screen for switching correspondent background.
 - Use Exit Control
    - Auth state of keyboard/gamepad usage for back to main menu. exp: `Escape`.
 - Control1
    - Auth state of keyboard/gamepad usage for next slide/selection or custom impl of WidgetLayer Calls  . exp: `E`.
 - Control2
    - Auth state of keyboard/gamepad usage for prev slide/selection or custom impl of WidgetLayer Calls  . exp: `Q`.
+++

---
## Screen Switching
- When screens change system get the preset in WidgetLayer list and apply changes.
- When we change the screen, we call OnExitLayer on the exiting screen.
- Set Up
    - Enable/Disable control buttons and set auths.
    - Enable/Disable/Set Back To Main Menu Block.
    - Open 3D World Background Screen.

---
In directory file find Initialization comment block. All menu button binding start in Initialization comment block.
## Initialization Comment Block
    - bind all of our  main menu buttons to corresponded widget/logic.

---
In directory file find OnPagesOpen comment block. All Data creations start in OnPagesOpen comment block.
## OnPagesOpen Comment Block
  -  exp : GenerateChapterItems (collapsed node).
  -  when data created, toggle the subject `WidgetLayer` `IsInitialized` boolean for stopping new generation.
  -  on data generation end, call the  `OnEnterLayer` in subject `WidgetLayer` for  manipulate/reset/load/update/etc... custom data actions.
  -  finally assign the current used `WidgetLayer` to  `CurrentWidgetLayer` variable.

---
In directory file find Controls comment block. All menu virtual/button controls start in Controls comment block.
## Controls Comment Block
- set up our dynamic page controls
    - Exit to Main Menu.
    - Invoke Control1 .
    - Invoke Control2 .
    - Virtual Buttons .