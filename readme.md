# learnings.md aka .plan

1. figured it to keep a lil place formyself here, inspired by https://dev.to/solidi/rediscovering-the-plan-file-4k1i
2. Tips / brew commands to [compile hashlink on M-series mac computers](https://community.haxe.org/t/building-haxe-on-mac-m1/3713/4), here is also [the vanilla instructions for building hashlink on linux/osx](https://github.com/HaxeFoundation/hashlink?tab=readme-ov-file#building-on-linuxosx)
3. To get colored output to terminal when using HXCPP on Windows, you can set the environment variable `ANSICON`: ([from tools/hxcpp/Log.hx in hxcpp!](https://github.com/HaxeFoundation/hxcpp/blob/45ee673796438ea5e8e57cb9ee4b7f47ea47d213/tools/hxcpp/Log.hx#L146))
    - On Windows, it's also recommended to be using [Clink](https://chrisant996.github.io/clink/)!
4. Snippet for pixel perfect HTML5 rendering for HaxeFlixel. [Further reading](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering)
    ```hx
    #if web
        // pixel perfect render fix!
        Application.current.window.element.style.setProperty("image-rendering", "pixelated");
    #end
    ```
5. You can add `-watch` as an arg when running/testing a Lime based project (openfl, haxeflixel, etc.), and it will auto-recompile anytime there's a file change in any of your source directories [code from lime/tools/utils/PlatformTarget.hx](https://github.com/openfl/lime/blob/9fb1817f99fea67d094d357e2b8782e6de231aac/src/lime/tools/PlatformTarget.hx#L65-L70). Each platform (CPP/HTML5/iOS) I believe they all use [`hxp.System.watch()` under the hood](https://github.com/openfl/hxp/blob/master/src/hxp/System.hx#L1354-L1401), which is NodeJS based, and seemingly directly from this Github repo https://github.com/mikeal/watch
6. On github actions, `hashFiles()` gives a different output on windows than it does on mac/linux, even when given the same input (at least as of 2024/02/03). So be careful with hashing on linux and then trying to restore via windows! 
7. You can generate Haxe type information to .xml by passing in `--xml output/path`. This is what Dox uses for documentation generation. However, you can also output json with `--json output/path`
