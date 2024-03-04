---
label: Apply
order: 65
icon: "/static/egg.png"
---

# How Get Output And Apply Changes ?

!!!
Output : Almost every screen have a `OnItemClicked` , `OnContentClicked` ,`OnChapterClicked`
!!!

Use this output events and apply your change with a custom blueprint

## Example : 
- Applying shopping need to add a `BP_CustomShop`.
-  On `WBPC_ShopSelector` add a variable by type `BP_CustomShop` end initialize on `BeginPlay` (GetActorOfClass).
- In `BP_CustomShop` add a custom logic and name it `OnItemPurchased`.
- In `WBPC_ShopSelector` find `OnItemClicked` and can get some item value in for `BP_CustomShop`.
- In `WBPC_ShopSelector` find `btn_purchase` button search the OnClicked event and call your custom event `OnItemPurchased`.
