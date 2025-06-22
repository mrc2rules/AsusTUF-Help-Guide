# Contributing
Want to contribute? Read below!

## Creating a new page
### Markdown
When creating a new page, ensure that it follows proper markdown format. 

If you prefer a visual markdown editing experience, you can use

- https://pandao.github.io/editor.md/en.html (Recommended)
- https://readme.so/editor

### Adding page to SUMMARY.md
> [!IMPORTANT]
> This step is **crucial** to ensure your page displays on the site's table of contents appropriately.

SUMMARY.md is available individually, at each language subdirectory. 
For example:-
`/linux/english-en/SUMMARY.md` OR `/windows/romanian-ro/SUMMARY.md`

It will look like this:
```
# Table of contents​

## PAGE GROUP 1​

* [Your page's title](page1/example1.md)
    * [Child page](page1/example2.md)

## PAGE GROUP 2

* [Your page's title](page1/example3.md)
    * [Child page](page1/example4.md)

```
---
Simply add a new line under the appropriate page group directory in the `* [Your page's title](page1/example1.md)` format. 

> [!NOTE]  
> The directory link must only include the section inside the language directory. 
> `* [Quickstart](linux/english-en/getting-started/quickstart.md)` ❌
>
> `* [Quickstart](getting-started/quickstart.md)` ✅



