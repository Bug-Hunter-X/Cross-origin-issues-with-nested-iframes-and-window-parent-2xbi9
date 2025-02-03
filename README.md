# Cross-origin issues with nested iframes and window.parent
This repository demonstrates a rather uncommon HTML bug related to cross-origin resource sharing (CORS) when using nested iframes and attempting to access parent elements via `window.parent`.

## The Bug
The core issue lies in the security restrictions imposed by browsers on cross-origin access.  When an iframe loads content from a different domain and tries to interact with its parent frame (or grandparent frame in the case of nested iframes) via `window.parent`, it often results in errors. This is especially tricky to debug when nested iframes are involved.

## Solution
Proper communication between origins requires implementing a suitable CORS policy on the server side of the resources loaded in the iframes.  Alternatively, more appropriate communication methods, like PostMessage API, should be used to exchange data safely across origins.
