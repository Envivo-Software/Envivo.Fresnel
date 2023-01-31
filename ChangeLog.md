# 2023-01-31: v0.10.1
## 🎁 New features:
- Model Config classes (alternative to inline Attribute Configurations)
- DefaultValuesAttribute for properties/parameters
- RequiredAttribute for properties/parameters

## 🐞 Fixes:
- Explorer height no longer shrinks when switching tabs (prevents UI jumping up/down)
- Explorer scrolling algorithm now takes off-screen offsets into account
- Explorer toolbar now uses tooltips from the view models
- Explorer "Save" button only enabled if object is Persitable _and_ has a Repository
- Explorer Tabs no longer crash if Domain Object has no members
- "Save All" now ensures correct repository is used for each Aggregate
- Date & Time editors now use custom DataFormatAttribute.DataFormatString, if available
- Ensure "Reload" button is disabled after restore is complete
- Ensure property "View" buttons are visible
- Ensure UI reflects new additions and removals to Collections
- Explorer toolbar now updates when object graph is dirty
- Value Objects: Prevent transient objects being edited after it's persisted
- Value Objects: Prevent Clear on persisted properties
- Value Objects: Corrected tooltip
- Now applies Display/Name to Classes, Collections, and Methods
- RunValidationsFor(value) now formats error message correctly
- SetPropertyCommand and SaveObjectCommand run all Validations that were explicitly delcared in Model code
- Undo: Reworked to use internal EventTimeLine
- Undo: DeterminObjectsToUndo now includes newly created objects
- Undo: Only undo changes upto the point where the Object was last saved
- Undo: Do not detach objects that were part of the original object graph
- Undo: Disassociate the new value from the property, and re-associate the original value
- Undo: Prevent Property Setter firing when restoring property values
- Undo: Ensure object Title Changes are refreshed in UI
- Undo:'Orphaned' explorers now removed from Workbench
- EventTimeLine entries now return correct affected objects
- Library: Prevent Fresnel assembly classes being added at run-time
- Library: Corrected Method Parameter names
- Method "Execute" button only enabled when all required Parameters are provided
- Method Parameter State now has correct Value

## 🎨 Improvements:
- Added padding to Boolean editors for improved aesthetics
- Ability to edit Value Objects by replacing them with cloned instances
- Editors now show red bar for [[REQUIRED]] Properties/Parameters
- Increase toolbar Message Badge counter limit
- Library panel: Scroll sub-menu options into view when menu is expanded
- Library panel: Reduced excessive tooltips being displayed
- Methods buttons: Reduced excessive tooltips being displayed
- When modal is cancelled, show Navigator if Workbench is empty
- Value Objects: Interactions now has icon to 'replace with copy'
- Only reset parameters prior to being display for user input

## 💨 Other:
- Corrected project URLs and copyright notices

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