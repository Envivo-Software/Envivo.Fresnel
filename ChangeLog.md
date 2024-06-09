# 2024-06-09: v0.94.2 (hotfix)

## 🐞 Fixes:
- Nuget WebAssembly Template: Ensure browser loads default page at startup
- Nuget Templates: All publish.bat scripts now use default Publish Profile

----------------------------------------
# 2024-05-20: v0.94.0

## 🎁 New features:
- Added Nuget Template for Web Server Application

## 🐞 Fixes:
- Startup: Allow user to close WinForms app if it crashes during startup
- Objects: Fixed regression around Property injection
- FileEditor: Now opens selector dialog
- About panel: Corrections for Preview/Demo versions
- UI: Removed broken font link

## 🎨 Improvements
- Model Configuration: Inline Attributes now take precedence over Model Config classes
- Library: Improved layout for namespace groups

----------------------------------------

# 2024-03-25: v0.92.5

## 🐞 Fixes:
- docs: Corrected dotnet template install step

----------------------------------------

# 2024-03-22: v0.92.4

## 🎁 New features:
- Added Nuget Template for non-Windows prototypes
- Added support for NamespaceDocs, to provide tooltips and styling to Library Namespace nodes
- Added support for C# Records (immutable once saved)
- Added support for PersistenceAttribute.IsImmutable on class properties
- File logging now controlled in Program.cs

## 🐞 Fixes:
- Collections: Contents now refresh when all collection items are replaced
- Collections: Corrected column sorting
- Collections: Value Objects become read-only after being saved
- Collections: Prevent fatal errors when editors lose focus
- EnumRadioEditor: Hide tooltip if empty
- EnumSelectEditor: Now handles Nullable<Enum>
- EnumBitwiseCheckboxEditor: Now handles Nullable<Enum>
- Explorers: Inline Objects on first tab are eagerly loaded
- Explorers: Allow null Inline Objects on first tab
- Explorers: Corrected exception when closing multiple explorers
- Explorers: Always eagerly load object/collection properties (unless they use RelationalQuerySpecifications)
- Explorers/Collections: Use inheritance depth when ordering Properties for inherited Classes
- ObjectSelectEditor: Update when Property is set to NULL
- ObjectSelectEditor: Show correct selection by default
- ObjectSelectEditor: Prevent exception when dropdown is repainted
- UrlEditor: Disable drop-down when necessary
- UI: Corrected custom CSS precedence
- UI: Corrected project name in title bar
- Services: Ensure custom Dependencies override existing registrations
- Search Form: Corrected Close button icon
- Search Form: Scroll form into view when it opens
- Search Form: Allow searching on Interface Types
- Aggregate References: Allow up-casting of generic Domain Classes
- Search Queries: Corrected filter clause building
- Nuget Templates: Include XML docs

## 🎨 Improvements
- Collections: Improved usability for wide tables (scrolling)
- Collections: Improved usability for in-line cell editing (edit icons)
- Collections: Allow subset of columns to be shown
- Collections: Added support for expandable rows
- Object Properties: Disable 'associate/link' action if UiAttribute.PreferredControl == Select
- Explorers: Added animation to show when explorer gets focus
- Explorers: Improved indentation/layout for Inline Objects
- Explorers: Prevent editing if PersistenceAttribute.IsImmutable is set
- UI styling: Added wait animation to hide UI lag
- UI styling: Changed icon for "View" actions
- UI styling: Updated aesthetics for Date/Time/DateTime editors in Doodle mode
- UI styling: Updated aesthetics for Boolean editor in Doodle mode
- UI: "Add/Create" actions now let User decide if Explorer windows should open immediately
- Search Form: Modal automatically closes if User chooses "View" action
- Search Form: Renamed "OK" to "Use selection", for clarity

## 💨 Other:
- Performance: Improved startup performance
- Upgraded 3rd-party NuGet dependencies

----------------------------------------

# 2023-11-29: v0.8.1

## 🐞 Fixes:
- Corrected logo markup for Nuget package

# 2023-11-27: v0.8.0
## ❗ BREAKING:
- Updated to .NET 8

## 🎁 New features:
- Relational Queries: Now supports  `RelationalQuerySpecificationAttribute` to load collection properties on-demand
- `IUnitOfWorkAdapter`: Allow granular `Save` operations (licence enabled feature)

## 🐞 Fixes:
- Change Tracking: Track objects linked/unlinked from Properties
- Change Tracking: Do not mark object as 'dirty' if same object is added then removed from collection
- Change Tracking: Do not mark object as 'dirty' if same object is removed then re-added from collection
- Collections: Throw exception if element type is unsupported
- Collections: Keep different Inline Collections in sync
- Dependency Injection: Corrected lifetime scopes for classes that implement IDomainDependency
- Number Editor: Corrected Range calculation for number properties
- Methods: Ensure Command Objects can be executed from UI
- Search Dialog: Opening search result now reloads fresh instance from persistent store
- Configuration classes: Now copes with interfaces higher up the inheritance chain
- Configuration classes: IAudit is now readonly by default (value object)
- UI: Inline Objects now cleared when property is set to null
- UI: Corrected tooltip for 'Remove'
- UI: Disable 'Remove' for Dictionary properties

## 🎨 Improvements
- Collections: Improved usability of "Remove" operation
- Collection propertiess: Allow viewing in separate explorer
- UI styling: Doodle mode now uses 'grid paper' background
- UI styling: Adjusted Boolean switch height in Doodle mode
- UI: First/Last columns in Collection are frozen
- Library: Tweaked columns to reduce string truncation
- Tooltips: Updated text for clarity
- Tooltips: Tweaked text for 'Restore' depending on whether object is transient or persistent
- Startup: Builder fluent API now allows configuring Services and pre-startup steps

## 💨 Other:
- Performance: Reduced component render cycles

# 2023-10-11: v0.75.6
## ❗ BREAKING:
- Updated for breaking changes in ModelTypes library
- Collection properties: Now uses [[CollectionAttribute]] to bind custom `Add/Remove` methods

## 🎁 New features:
- BlazorWinFormBuilder: Ability to enable/disable features
- Workbench: Added panning and zoom, to help navigate a busy workbench
- Library: Now uses mega-menu to improve usability
- Library: Allow classes to be hidden in Library
- Messages Panel: Exceptions need acknowledgement for Message Counter to turn green 
- Messages Panel: Toast messages appear for key messages
- UI styling: Use 'doodle' style for Preview and Designer editions
- Explorers: Support custom icons and accent colours
- Explorers: Allow card minimise and maximise
- Search Dialog: Added "Re-run Search" toolbar option
- Search: Now uses IPagedFiltering if Repository implements it
- Methods: Support for rendering Methods alongside related Properties
- Methods: Show MethodAttribute.MandatoryPromptText if available
- Methods: Show MethodAttribute.UnsavedChangesPromptText when parent object is dirty
- Command Dialogs: Added support for ICommandObject instances
- Strings: Added support for URLs
- Strings: Added support for Images
- Strings: Added support for Files

## 🐞 Fixes:
- Session restart: Prevent explorer exceptions after Ctrl-F5
- Library: Exclude namespaces that don't have visible classes
- Library: Handle mismatched namespaces in Domain Model
- Explorers: Corrected auto-scrolling positioning
- Explorers: Corrected "Save" tooltip when changes are detected
- Explorers: Disable "Save" if Feature is disabled during boostrap
- Explorers: Allow "Reload" if object has persistent storage
- Explorers: Do not render properties that belong to other classes (inheritance siblings)
- Explorers: Allow Collections to be explored (in case they are returned by a method)
- Search: Use explicit SearchClass, if selected by user
- Search Results: No longer constantly fire StateHasChanged 
- Reload: Handle exception when persistent Collection Property contains null
- Properties: Allow PropertyTypes that are NOT Domain classes
- Collection properties: Corrected 'Remove' interaction
- Collection properties: Corrected exception when undoing collection changes for persistent objects
- Collection properties: Allow 'Add', even if 'Create' is not allowed
- Collections: Handle AggregateReference sub-types
- Collections: Corrected inline editing
- Collections: Prevent column widths jumping around when cells are edited
- Collections: Cope with contents changes trigged by Method calls
- Enums: Show Friendly Name
- ObjectSelectEditor: Show Collection Elements for objects not already in the UI
- NumberEditor: Show Currency symbol, if applicable
- NumberEditor: Default Min/Max based on property Type
- Methods: Handle async methods that do not return values
- Method Dialog: Reset parameters before dialog appears
- Method Parameters: Use consistent icon for 'Clear'
- Method Parameters: Clear now works
- Shutdown: Allow shutdown if app crashes internally

## 🎨 Improvements:
- BlazorWinFormBuilder: Added BuildServiceProvider(), so consumers can access dependencies before launching the UI
- Startup: New loading page
- Workbench: Spinner animations for long-running opeations
- Workbench toolbar: Now anchored to top of viewport, and less intrusive
- Messages Panel: Improved layout and formatting
- Messages Panel: Only show messages for key events
- Library: Improved Namespace titles, so that nested namespaces are clearer
- Library: Domain Services and Domain Classes now appear in same namespaces
- Library: Support custom icons and accent colours
- Library: Allow classes to be hidden in Library, but visible in Workbench
- Explorers: Improved animation to show where Explorers are added/removed from UI
- Explorers: Disable editing of Aggregates and Parents when displayed inline
- Explorers: Show information icon before description
- Explorers: Automatically close Explorers for orphaned objects for property/collection changes
- Collections: Now shows 'Type Name' column, if collection supports multiple types 
- Collections: Indicate non-editable cells when grid contains polymorphic types
- Collections: Added "View" button, so Collections can appear in separate Explorer
- Search Results: Removed radio option, as "View" button is used to expand an item
- Search Results: Include Total Count in message
- Query Specifications: Improved identification of overload method when injecting parent object as context
- Methods: Show Search Dialog immediately for Methods with a single object/collection parameter
- Methods: Factory methods, and instance Methods all use common UI behaviours
- Methods: Factory methods, and instance Methods all use common UI behaviours
- Methods dialog: Increase width if any parameter shows an inline collection
- About Dialog: Show licence details
- Shutdown: Prompt to save changes before shutting down

## 💨 Other:
- Updated to .NET 7.0
- Upgraded all 3rd party packages


# 2023-05-29: v0.24.7
## 🐞 Fixes:
- Library: Restored Search Filter functionality
- Undo: Stop using DLR when restoring from repository
- Search Results dialog: Prevent exception if OK clicked without selecting a Search Result item
- Search Results dialog: Prevent exception when cancelling selection

## 🎨 Improvements:
- Messages panel: Added quotes and consistency to content


# 2023-05-08: v0.24.5
## 🎁 New features:
- Added support for IAggregateReference<T>
- Refactored BlazorWinformBuilder into separate project
- Display spinner animation for long running operations
- Now supports async methods from the UI

## 🐞 Fixes:
- Allow Container configuration even if IServiceCollection isn't present
- XML documentation: Read from embedded resource if available
- Method Dialog: Use default values for Optional Parameters
- Method Dialog: Prevent double-clicks invoking method multiple times
- Method dialog: Report errors if Method Parameter can't be set
- Properties: Corrections with FilterQuerySpecification and calling GetResultsAsync(parentObject)
- Search results: Allow primitive column sorting 
- Load Property: Handle null results
- Property Search Query: Report errors if query fails
- ValueObject: Don't allow null to be cloned

## 🎨 Improvements:
- Method Dialog: Prevent input fields losing focus, where possible
- Remove "Async" prefix from async Method names

## 💨 Other:
- Performance: Added RenderOptimiser to reduce render cycles
- Performance: Prevent in-line lambda delegates being created on every render cycle
- Performance: Reduce string creations
- Performance: Optimised CascadingValues
- Performance: Other rendering optimisations


# 2023-02-11: v0.11.1
## 🎁 New features:
- Objects that are added/removed from collections are no longer considered dirty
- "Save All" is only enabled for visible Explorer cards
- Collection dirty status now reset correctly
- Opening properties or persistent objects now marks contents as persistent too

## 🎨 Improvements:
- Better handling of Explorer auto-scrolling
- Search Dialogs now have constant width
- Internal stateless Commands now have InstancePerLifetimeScope

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
