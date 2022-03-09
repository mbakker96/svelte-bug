# Compiling bug

We have two seperared projects that share a few compoments (share folder) and share the node_modules. Both projects do have there own tsconfig.json and rollup file. this is to add some flexibility. 

When we import a svelte file from the share folder that includes also a typescript file the compliler gives the following error: 

I know that problem can be solved by adding the share folder to the tsconfig. But we don't want to do that. becease then it checks very file in the share, but we only want to check the files that is being used by the project itself. 

Does someone has a sollution for this? 

``` 
src/project-b/App.svelte → public/build/bundle.js...
[!] Error: Unexpected token (Note that you need plugins to import files that are not JavaScript)
src/share/utils/utils.ts (2:28)
1: 
2: export function capatilize(s: string): string {
                               ^
3:   return s.toUpperCase()
4: }
Error: Unexpected token (Note that you need plugins to import files that are not JavaScript)
    at error (/Users/martijn/Projects/typescript-probleem/node_modules/rollup/dist/shared/rollup.js:198:30)
    at Module.error (/Users/martijn/Projects/typescript-probleem/node_modules/rollup/dist/shared/rollup.js:12477:16)
    at Module.tryParse (/Users/martijn/Projects/typescript-probleem/node_modules/rollup/dist/shared/rollup.js:12853:25)
    at Module.setSource (/Users/martijn/Projects/typescript-probleem/node_modules/rollup/dist/shared/rollup.js:12756:24)
    at ModuleLoader.addModuleSource (/Users/martijn/Projects/typescript-probleem/node_modules/rollup/dist/shared/rollup.js:22220:20)

➜  typescript-probleem 
```