Register plugin in the Admin Area application.

Add the dependency at `@swapnilmmane/pb-iframe` in project root's package.json


Let's make the following changes in `apps/admin/code/src/plugins/pageBuilder/editorPlugins.ts` file:

```ts title="apps/admin/code/src/plugins/pageBuilder/editorPlugins.ts" {4,7-8}
(...)

// Import the `iframe` element and it's settings
import iframeElement, { iframeSettings } from "@swapnilmmane/pb-iframe/admin";

export default [
    iframeElement(),
    iframeSettings,
    // Rest of the plugins
    (...)
];
```

Also in `apps/admin/code/src/plugins/pageBuilder/renderPlugins.ts` file:

```ts title="apps/admin/code/src/plugins/pageBuilder/renderPlugins.ts" {4,8}
(...)

// Import the `iframe` element
import iframeElement from "@swapnilmmane/pb-iframe/render";

export default [
    // Elements
    iframeElement(),
    // Rest of the plugins
    (...)
];
```

In the Website application, simply register plugin by making the following changes in the `apps/website/code/src/plugins/pageBuilder.ts` file:

```ts title="apps/website/code/src/plugins/pageBuilder.ts" {5,10}
// Some code is removed for the sake of brevity.
(...)

// Import `iframe` element
import iframeElement from "@swapnilmmane/pb-iframe/render";

export default [
    (...)
    // Page elements
    iframeElement(),
    (...)
];
```