# Contributing

Want to contribute? Read below!

# Table of contents

1. [Introduction](#introduction)
2. [Guidelines](#guidelines)
    1. [Language](#language)
    2. [Markdown](#markdown)
3. [Creating a new page](#newpage)
4. [Contribute to an existing page](#oldpage)

## Introduction

- If you just wish to offer suggestions and ideas, you can:
   - [Create a new GitHub issue](https://github.com/mrc2rules/AsusTUF-Help-Guide/issues/new)
   - [Message us via ModMail on Reddit](https://www.reddit.com/message/compose?to=%2Fr/Asustuf&subject=AsusTUF%20Guide%20Contribution%20Request&message=Hello!%20I%20have%20some%20suggestions%20and%20ideas%20for%20the%20guide.%20TYPESUGGESTIONSHERE%20)
 
- If you want to contribute directly, you should:
  - Read [Guidelines](#guidelines) first and [fork this repository](https://github.com/mrc2rules/AsusTUF-Help-Guide/fork) 
  - Then, you can:
       - [Create a new page](#newpage), or
       - [Contribute to an existing page](#oldpage)
  - Finally, create and submit a pull request.

## Guidelines <a name="guidelines"></a>

### Language <a name="language"></a>

Please ensure that all written content:
- Follows standard grammar and writing conventions for the target language. 
- Uses professional, clear, and easy-to-understand language while avoiding slang or regional idioms unless context requires it. 

### Markdown <a name="markdown"></a>

Please ensure all written content follows [standard Markdown syntax](https://www.markdownguide.org/basic-syntax/). 

If you prefer a visual markdown editing experience, you can use
- https://pandao.github.io/editor.md/en.html (Recommended)
- https://readme.so/editor

## Creating a new page <a name="newpage"></a>

After proofreading your newly written content and ensuring it follows proper markdown standards, include the following code at the top of your page.
```
---
hidden: true
---
```
This is required because pages need to be manually reviewed and properly formatted via the GitBook visual editor to appear well-organized and visually appealing. GitBook’s visual editor supports various content blocks that help your content look clean, organized, and visually appealing. 

> [!IMPORTANT]
> You'll need to add your page to the `SUMMARY.md` file so that it displays on the site's table of contents.
> 
> `SUMMARY.md` is available individually, at each language subdirectory. 
> <br>For example: `/linux/english-en/SUMMARY.md` OR `/windows/romanian-ro/SUMMARY.md`



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
Next, simply add a new line under your content-relevant page group in the `* [Your page's title](page1/example1.md)` format.

If none of the groups include your content, you may add a new group by simply adding `## GROUP NAME HERE` in a new line.

> [!NOTE]  
> The directory link must only include the section inside the language directory.
> 
> `* [Quickstart](linux/english-en/getting-started/quickstart.md)` ❌
>
> `* [Quickstart](getting-started/quickstart.md)` ✅
>

## Contribute to an existing page <a name="oldpage"></a>

lorem ipsum
