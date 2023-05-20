---
sidebar_label: 'Layout'
---

Use layouts to easily create some content

Layouts use an unlayer editor plugin that help to create beautifful contents. 

See <a href="https://unlayer.com/" target="new">here</a> for more detail about the way to use the unlayer web page editor
<br/>

1. Create a new blank layout or use a template
2. Customize your content and click on update
3. Your layer can be used in media sequence

![widget](/img/screen1.png)

## Use dynamic variables

You can use [mustache](https://www.npmjs.com/package/mustache) variables in your content and then call an online service to change the values of the variables.

When you call the online service to change the value of the variables, your screen will be re-rendered automatically and new values will be displayed

Create a mustache variable like {{ma_variable}} inside your layout content, then you can fill the value using a Rest Service

the code below explains how to do that on server side

```jsx title="Exemple using node"
function HelloDocusaurus() {
    const axios=require('axios');
    axios.post('https://us-central1-castreactor.cloudfunctions.net/layout/layoutData/YOUR_BRAND_ID/YOUR_DEVICE_ID',
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
