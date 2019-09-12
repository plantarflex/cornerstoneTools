# Modules

A module is a namespaced storage object in the `store` that contains the following properties:

| Property                                      | Requirement | Description                                                                                                                                                                                                                                                                                                                                                          |
| --------------------------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| configuration                                 | Mandatory   | An object that configures the module for app-wide usage. Configuration is intended to be manipulated by methods both internal and external to `cornerstoneTools`.                                                                                                                                                                                                    |
| state                                         | Optional    | An object that Ssores the module's current state. State is intended to only be manipulated by `cornerstoneTools` and `cornerstoneTools` plugins. There is no vigorous structure state must follow, as it will be specific to what the module is trying to accomplish.                                                                                                |
| getters                                       | Optional    | An object comprised of functions that query state. Getters can be used for more complex queries of the state (e.g. to yield a value that references a specific `cornerstone` enabled element). Top level primitives that require no calculation should instead by accessed by `const property = state.property`, as this reduces boilerplate in implementation code. |
| setters                                       | Optional    | An object comprised of functions that modify state. Setters can be used for more complex input (e.g. `push` object `x` to array `y`). Top level primitives should be set by `state.property = value`, as this reduces boilerplate in implementation code.                                                                                                            |
| onRegisterCallback (name)                     | Optional    | This function is called when the module is registered to the `cornerstoneTools` `store`. It is used to perform any global initialization the modules requires. The `name` the module was given upon registration is passed to the callback.                                                                                                                          |
| enabledElementCallback (enabledElement)       | Optional    | This function is called once for each `Enabled` element upon registering the module, and again any time a new `Enabled` element is added to the `cornerstoneTools` instance. The `Enabled` Element is passed to the callback.                                                                                                                                        |
| removeEnabledElementCallback (enabledElement) | Optional    | This function is called whenever an `Enabled` element is removed from the `cornerstoneTools` instance, allowing cleanup of unneeded data. The `Enabled` Element is passed to the callback.                                                                                                                                                                           |

{% include "./global-configuration.md" %}
{% include "./cursors.md" %}
{% include "./segmentation.md" %}