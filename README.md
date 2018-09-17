# NativeScript Angular Sample Project 

This demo can be used to demonstrate the problem when using webpack in combination with SASS. 

## Setup

This project was generated using the angular template seed: 

```
tns create my-app-name --ng
```

After that webpack was installed to be used for building the app. Therefore I've followed the documentation: 
https://docs.nativescript.org/performance-optimizations/bundling-with-webpack

In addition, I've installed the SASS Plugin for NativeScript. Therefore I've follwowed this documentation: 
https://docs.nativescript.org/ui/theme#sass-usage

## Reproduce the problem
 
The problem we were facing when using webpack and SASS in combination in a NativeScript project, is that the scss files are not compiled when building the app with e.g. `tns build ios --bundle` the hook is skipped because of the `--bundle` flag. Since the compilation is skipped webpack does not find the compiled css files. According to the SASS Usage documentation of NativeScript components should reference the css file and not the scss file - which works fine, when not using webpack. 

The error that will appear: 

```
ERROR in ./item/item-detail.component.ts
Module not found: Error: Can't resolve './item-detail.css' in 'app/item'
 @ ./item/item-detail.component.ts 17:21-49
 @ ./app.module.ts
 @ ./main.ts
 ```
 