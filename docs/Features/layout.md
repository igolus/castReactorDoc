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

![remoteControl1](/img/screen1.png)

## Use dynamic variables

You can use [mustache](https://www.npmjs.com/package/mustache) variables in your content and then call an online service to change the values of the variables.

When you call the online service to change the value of the variables, your screen will be re-rendered automatically and new values will be displayed

Create a mustache variable like {{variable}} your layout content, then the code below explains how to do that on server side

const axios=require('axios');
axios.post('http://localhost:5001/castreactor/us-central1/layout/layoutData/hxRHr6ESnqW5OH6O9tEI/SksjeUeaz9K9Y82pxOrH',
{
"ma_variable": "ma_variable_value"
},
{
headers: {
'Content-Type': 'application/json',
'Authorization': '6c983c1d-dcf9-4c43-899c-659b46fa4c6b'
}
}
)
.then(function (response) {
console.log("update done");
})
