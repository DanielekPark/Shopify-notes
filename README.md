# Notes Shopify Partners 

Creating a Shopify Partners Store using Theme kit

- Shopify Partners account uses HTML, CSS, and [Liquid](https://shopify.github.io/liquid/basics/introduction/)

1. Install [Shopify theme kit](https://shopify.dev/docs/themes/tools/theme-kit/getting-started) if you haven't already

2. Make a [Shopify Partners account](https://partners.shopify.com/organizations)

3. Choose a [Shopify theme](https://shopify.dev/docs/themes/tools/online-editor)

Run on the command line, when you have the following: 
-Password
-Shopify Store URL
-theme id
```bash
theme get --password=<Password> --store=<Shopify Store URL> --themeid=<theme number>
```

In the folder that was created, create a CSS file (e.g. custom-styles.css) inside the assets folder. Add the code to theme.liquid
```html
{{ 'custom-styles.css' | asset_url | stylesheet_tag }}
```

-Run on the command line, to see changes/featured added. You may need to refresh the browser. 
```bash
theme watch --allow-live
```

-Some Vscode extensions may add unexpedted code to one of the Shopify pages (e.g. '{')

-If there are any changes to Shopify, or if these steps that do not work, or if you have any suggestions, please feel to contact me at daniel.ek.park@gmail.com

-HAPPY CODING!!!