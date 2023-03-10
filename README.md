# Shopify Partners theme development 

Creating a Shopify Partners Store using Theme kit

Shopify Partners account uses HTML, CSS, and [Liquid](https://shopify.github.io/liquid/basics/introduction/)

Install [Shopify theme kit](https://shopify.dev/docs/themes/tools/theme-kit/getting-started) if you haven't already

Make a [Shopify Partners account](https://partners.shopify.com/organizations)

Once logged in the dashboard: 
1. Click stores on the left side navbar
2. Click add store
3. Click create development store and provide the necessary information


Next click online store and click themes, click add to choose a theme

Required parts store URL, themeid, and password
- Get the URL of the partner's store, click on the eye icon next to the Online Store

- Get the themeid, go to the tab that was opened from the previous step and right click and click on View page source. Press ctrl + f for Windows; command + f for Mac, type in themeID to get the id. 

- To get the password go to the Theme Access app page on the [Shopify App Store](https://apps.shopify.com/theme-access?shpxid=70bc21e3-A0A8-4C84-A456-BA522B77D06E)

- On the Theme Access app page, click Add app.
- In your Shopify admin, to authorize the use of the app, click Install app.

- In the admin dashboard click the 3 dots next to the Customize button and click download theme file. Provide an email and check your email. 

- Download and extract the file

Once extracted, inside the folder and create config.yml file in the root directory. In the root directory add the following: 
```yml
development:
  password: password might start with shptka
  theme_id: "themeid"
  store: yourshopifyurl.myshopify.com
```
PLEASE NOTE THE theme_id SHOULD BE IN QUOTES

In the assets folder, create a CSS file (e.g. customstyles.css)

In theme.liquid file located in the layout folder, add the code:
```html
{{ 'customstyles.css' | asset_url | stylesheet_tag }}
```
BELOW 
```html
{{ 'theme.css' | asset_url | stylesheet_tag }} 
```
OR BELOW 
```liquid
 <!-- CSS
==================================`================ -->
```
In the CSS stylesheet that was created and located in assets folder, write provide the custom CSS to override the provide Shopify theme. 

-Run on the terminal/command prompt to see the changes added. You may need to refresh the browser everytime new a new line of CSS is added. 
```bash
theme watch --allow-live
```

## Using Shopify theme init
Login to your account and get the name of your Shopify store
shopify theme dev --store https://yourshopifystore.myshopify.com/

Next run
```bash
shopify theme init
```

If a local repo has been created through and there's an error try running
```bash
SHOPIFY_CLI_BUNDLED_THEME_CLI=true shopify theme dev
```

-If there are any changes to Shopify, or if these steps that do not work, or if you have any suggestions, please feel to contact me at daniel.ek.park@gmail.com

<!--
https://shopify.dev/docs/themes/tools/cli
Run on the command line, when you have the following: 
-Password
-Shopify Store URL
-theme id
```bash
theme get --password=<Password> --store=<Shopify Store URL> --themeid=<theme number>
-->