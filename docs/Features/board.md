---
sidebar_label: 'board'
---

You can define boards to display events relative to your business

# Create you board 

![](/img/board.png)

Create the board

![](/img/board2.png)

Update your board configuration

![](/img/board4.png)

Define your custom columns 

![](/img/board3.png)


You can customize your column display using css

![](/img/board6.png)

See an example with two colums: 'incoming' and 'ongoing'

```
h3, .h3 {
font-size:35px !important;
}

.incoming {
font: italic small-caps bolder 16px/3 cursive;
background-color: #ADD8E6;
text-align: center;
border-radius: 2% 7% 5% 2%;
box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px, rgba(10, 37, 64, 0.35) 0px -2px 6px 0px inset;
}

.incoming-item {
border-radius: 1%;
box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}

.incoming-title {
border-radius: 1%;
box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}

.ongoing {
font: italic small-caps bolder 16px/3 cursive;
background-color: #ADD8E6;
text-align: center;
border-radius: 2% 7% 5% 2%;
box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px, rgba(10, 37, 64, 0.35) 0px -2px 6px 0px inset;
}

.ongoing-item {
border-radius: 1%;
box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}

.ongoing-title {
border-radius: 1%;
box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}

.dialog {
text-align: center;
background-color: blue;
}

.header {
background-color: #FFFFFF;
}
```
Here is your board 

![](/img/board5.png)

# Fill events in your board

To populate your board you need to send event using our rest API

See below example of code.

You can find [here](https://dashboard.castreactor.com/assets/CastReactorBoardUpdate.postman_collection.json) a postman collection to populate your board

Here is an example using Node js

```
const axios=require('axios');
axios.post('http://localhost:5001/castreactor/us-central1/board/displayEvent/YOUR_BRAND_ID',
{
  "idDisplay": "Incoming 1",
  "status": "incoming",
  "contentDisplay": "detail 1",
  "targetBoards": [
    "YOUR_BOARD_ID"
  ]
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
```


