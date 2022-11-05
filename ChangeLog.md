# 2022-11-05: v0.9.0
## 🔌 API changes:
- Bootstrap: FresnelContainerBuilder now allows consumer to override Logging provider

## 🐞 Fixes:
- Allow classes to be created if they have a default ctor, even if they're created under a parent product
- Don't allow classes to be created independently if they require an arg that is a Domain Object
- "Close card -> Cancel Changes" now un-does all changes made to the object being closed
- "Close card -> Cancel Changes" no longer gets into endless loop
- "Close card -> Cancel Changes" detects changes made internally by Methods (e.g. property and/or collection changes that are part of the method's logic)
- "Reload" option now restores object's original state
- Undoing "Property Change" for *reference objects* now restores the original object
- Undoing "Property Change" for read-only properties is now skipped
- Property with `InlineObject` attribute now shows animation when it is set
- CollectionTracker prevents duplicate Events being recorded
- Prevent editing read-only properties in Collection grid
- Corrected exception when setting Property that was previously cleared (i.e. set to null)
- Method buttons only show tooltip if actual method has comments
- Corrected EULA link in "About" dialog

## 🎨 Improvements:
- Explorer cards: "Save" option now only enabled for 'top-level' Aggregates or objects
- Explorer cards: Now scrolls new Explorer panels into full view
- Explorer cards: Inner Tabs with tall contents now force card to scroll into full view
- Properties: Setting a Property with a *new object* now asks if existing property value should be replaced
- Properties: Replaced "Open XXX in a new panel" with "See full details for XXX", and changed icon to "..."
- Watermark animation appears less frequently

## 💨 Other:
- Upgraded 3rd-party NuGet dependencies
- Public classes marked as 'sealed'
- ToArray() replaced with ToList() where acceptable


# 2022-09-01: v0.8.13
Initial Preview Release 