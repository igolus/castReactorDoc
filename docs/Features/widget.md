---
sidebar_label: 'widget'
---

Use widgets to easily create some content with HTML, CSS and javascript

1. Create a new blank layout or use a template
2. Associate your html css and javascript code
3. Your widget can be used in media sequence

![layout](/img/screen3.png)

## Use dynamic variables

You can use [mustache](https://www.npmjs.com/package/mustache) variables in your content and then call an online service to change the values of the variables.

When you call the online service to change the value of the variables, your screen will be re-rendered automatically and new values will be displayed

Create a mustache variable like {{ma_variable}} inside your layout content, then you can fill the value using a Rest Service

the code below explains how to do that on server side

```jsx title="Exemple using node"
function HelloDocusaurus() {
    const axios=require('axios');
    axios.post('https://us-central1-castreactor.cloudfunctions.net/widget/widgetData/YOUR_BRAND_ID/YOUR_WIDGET_ID',
        {
            "ma_variable": "ma_variable_value"
        },
        {
            headers: {
                'Content-Type': 'application/json',
                'Authorization': 'YOUR_AUTHORIZATION_KEY'
            }
        }
    )
    .then(function (response) {
        console.log("update done");
    })
}
```
