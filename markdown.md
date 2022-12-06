# Learn Markdown


- [Learn Markdown](#learn-markdown)
  - [Syntax:](#syntax)
  - [Helful Resources](#helful-resources)
  - [Bold and Italic](#bold-and-italic)
        - [You can make sth italic with: `*italic*`](#you-can-make-sth-italic-with-italic)
        - [You can make sth bold with: `**Bold**`](#you-can-make-sth-bold-with-bold)
        - [You can make sth both with: `***both***`](#you-can-make-sth-both-with-both)
  - [Image](#image)
  - [Making tabs like Menu](#making-tabs-like-menu)




## Syntax:


- **Headline**: Bold from high to low like `h1... h6` is gonna be `number of hashtag #`
- **Link**: `[text](url)` like `[Ehsan Website](https://ehsanabt.github.io)`

- [Ehsan](https://ehsanabt.github.io)


- **Code**
  - Inline code: This is `inline code`
  - Multiline code: use when we have multi line of code like ```html code```



- **Collapsable Statement**: 
  <details>
    <summary> HTML Example</summary>
    
    ```html 
        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <title>Document</title>
            <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
            <meta name="description" content="Description" />
            <meta
            name="viewport"
            content="width=device-width, initial-scale=1.0, minimum-scale=1.0"
            />
            <link
            rel="stylesheet"
            href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css"
            />
        </head>
        <body>
            <div id="app"></div>
            <script>
            window.$docsify = {
                name: "Ehsan's Documentation",
                repo: "https://github.com/ehsanabt/ehsanabt",
                loadSidebar: true,
                search: "auto", // default
            };
            </script>
            <!-- Docsify v4 -->
            <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
            <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
        </body>
        </html>
    ```

  </details>

## Helful Resources

- [Cheatsheet](https://www.markdownguide.org/cheat-sheet/)


## Bold and Italic
##### You can make sth italic with: `*italic*`
##### You can make sth bold with: `**Bold**`
##### You can make sth both with: `***both***`

## Image
its syntax is: `![text](address/name.png)`

## Making tabs like Menu????????
<tabs>
<TabItem value="Ehsan" label="EA" default>
console.log("Ehsan")
</TabItem>
</tabs>
