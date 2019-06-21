# TypeScript 3.5 error

tsc output:

```
node_modules/scroll-behavior-polyfill/dist/index.d.ts:5:9 - error TS2669: Augmentations for the global scope can only be directly nested in external modules or ambient module declarations.

5 declare global {
          ~~~~~~


Found 1 error.
```

# patch that fixes the issue

```patch

diff --git a/node_modules/scroll-behavior-polyfill/dist/index.d.ts b/node_modules/scroll-behavior-polyfill/dist/index.d.ts
index 0ef8139..5ef52be 100644
--- a/node_modules/scroll-behavior-polyfill/dist/index.d.ts
+++ b/node_modules/scroll-behavior-polyfill/dist/index.d.ts
@@ -10,4 +10,5 @@ declare global {
         };
     }
 }
+export {};
```
