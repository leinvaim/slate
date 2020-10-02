# Instances

## Instance object

> Example of Instance object

```json
{
  "id": 4,
  "created": "2020-08-24T01:45:10.930695Z",
  "updated": "2020-08-24T01:45:33.687595Z",
  "workflow_id": 2,
  "instance_steps": [
    {
      "step": 1,
      "status": "current",
      "progress": "50",
      "updated": "2020-08-24T01:45:33.745083Z",
      "content": [
        {
          "id": "1",
          "type": "identifier",
          "label": "Room Number:",
          "value": ""
        },
        {
          "id": "2",
          "type": "heading",
          "label": "Room Inspection Check"
        },
        {
          "id": "3",
          "type": "information",
          "label": "Room inspection required after cleaning personnel finished."
        },
        {
          "id": "4",
          "type": "time_date",
          "label": "Date and Time of Inspection",
          "value": ""
        },
        {
          "id": "5",
          "type": "checkbox",
          "label": "Bathroom Inventory",
          "options": ["2 x Fresh Towels"],
          "value": "2 x Fresh Towels",
          "dependencyCondition": []
        },
        {
          "id": "6",
          "type": "radio_button",
          "label": "Is Room Guest ready?",
          "options": ["Yes", "No"],
          "value": "",
          "dependencyCondition": []
        },
        {
          "id": "7",
          "type": "media",
          "label": "Photo of Issue",
          "attachmentText": "Tiikr logo",
          "photo": "Tiikr_Logo_AboveBelow_350SQ_whiteSpace.jpg",
          "subtype": "",
          "value": "",
          "url": "https://tiikr.com/example.jpg"
        },
        {
          "id": "8",
          "type": "signature",
          "label": "Inspector Name and Signature",
          "value": "",
          "textEntryValue": "Test",
          "url": ""
        }
      ]
    },
    {
      "step": 2,
      "status": "pending",
      "progress": "0",
      "updated": "2020-08-24T01:45:10.943959Z",
      "content": [
        {
          "id": "1",
          "type": "heading",
          "label": "Generic Step 2"
        },
        {
          "id": "2",
          "type": "checkbox",
          "label": "Which Fruit do you prefer?",
          "options": ["Orange", "Apple", "Peach"],
          "value": "",
          "dependencyCondition": []
        }
      ]
    },
    {
      "step": 3,
      "status": "pending",
      "progress": "0",
      "updated": "2020-08-24T01:45:10.949183Z",
      "content": [
        {
          "id": "1",
          "type": "heading",
          "label": "Generic Step 3"
        },
        {
          "id": "2",
          "type": "signature",
          "label": "Enter Name and Sign",
          "value": "",
          "textEntryValue": "",
          "url": ""
        }
      ]
    }
  ]
}
```

| Attributes     | Type   | Description                                 |
| -------------- | ------ | ------------------------------------------- |
| id             | number | Instance id                                 |
| created        | string | Instance created date                       |
| updated        | string | Instance last updated date                  |
| workflow_id    | number | Workflow id                                 |
| instance_steps | array  | An array of Instance steps in this workflow |

## Retrieve an Instance

```python
import requests

request = requests.get("https://manage.tiikr.com/api/v1/workflows/<workflow_id>/instances/<instance_id>", auth=(username, password))
response = request.json()

```

```javascript
let request = new XMLHttpRequest();

request.open(
  "GET",
  "https://manage.tiikr.com/api/v1/workflows/<workflow_id>/instances/<instance_id>",
  true
);
request.withCredentials = true;
request.setRequestHeader("Authorization", "Basic " + btoa("username:password"));

request.send();
request.onload = () => {
  console.log(JSON.parse(request.response));
};
```

> Response

```json
{
  "success": true,
  "data": {
    "id": 4,
    "created": "2020-08-24T01:45:10.930695Z",
    "updated": "2020-08-24T01:45:33.687595Z",
    "workflow_id": 2,
    "instance_steps": [
      {
        "step": 1,
        "status": "current",
        "progress": "50",
        "updated": "2020-08-24T01:45:33.745083Z",
        "content": [
          {
            "id": "1",
            "type": "identifier",
            "label": "Room Number:",
            "value": ""
          },
          {
            "id": "2",
            "type": "heading",
            "label": "Room Inspection Check"
          },
          {
            "id": "3",
            "type": "information",
            "label": "Room inspection required after cleaning personnel finished."
          },
          {
            "id": "4",
            "type": "time_date",
            "label": "Date and Time of Inspection",
            "value": ""
          },
          {
            "id": "5",
            "type": "checkbox",
            "label": "Bathroom Inventory",
            "options": ["2 x Fresh Towels"],
            "value": "2 x Fresh Towels",
            "dependencyCondition": []
          },
          {
            "id": "6",
            "type": "radio_button",
            "label": "Is Room Guest ready?",
            "options": ["Yes", "No"],
            "value": "",
            "dependencyCondition": []
          },
          {
            "id": "7",
            "type": "media",
            "label": "Photo of Issue",
            "attachmentText": "Tiikr logo",
            "photo": "Tiikr_Logo_AboveBelow_350SQ_whiteSpace.jpg",
            "subtype": "",
            "value": "",
            "url": "https://tiikr.com/example.jpg"
          },
          {
            "id": "8",
            "type": "signature",
            "label": "Inspector Name and Signature",
            "value": "",
            "textEntryValue": "Test",
            "url": ""
          }
        ]
      },
      {
        "step": 2,
        "status": "pending",
        "progress": "0",
        "updated": "2020-08-24T01:45:10.943959Z",
        "content": [
          {
            "id": "1",
            "type": "heading",
            "label": "Generic Step 2"
          },
          {
            "id": "2",
            "type": "checkbox",
            "label": "Which Fruit do you prefer?",
            "options": ["Orange", "Apple", "Peach"],
            "value": "",
            "dependencyCondition": []
          }
        ]
      },
      {
        "step": 3,
        "status": "pending",
        "progress": "0",
        "updated": "2020-08-24T01:45:10.949183Z",
        "content": [
          {
            "id": "1",
            "type": "heading",
            "label": "Generic Step 3"
          },
          {
            "id": "2",
            "type": "signature",
            "label": "Enter Name and Sign",
            "value": "",
            "textEntryValue": "",
            "url": ""
          }
        ]
      }
    ]
  }
}
```

This endpoint retrieves an instance of a particular workflow.
You will need to know the workflow_id and instance_id that you want to retrieve.

### HTTP Request

`GET` `/api/v1/workflows/<workflow_id>/instances/<instance_id>`

### URL Parameters

| Parameter   | Description                                        |
| ----------- | -------------------------------------------------- |
| workflow_id | Workflow id that you want to get the instance from |
| instance_id | Instance id that you want to retrieve              |
