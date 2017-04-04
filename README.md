# Basic JSON

### JSON Stands for JavaScript Object Notation

### What is JSON? 
- JavaScript is a programming language. 
- JSON was originally created to hold structured data to be used in JavaScript. 
- JSON is a lightweight data-interchange format. 
- It is easy for humans to read. 
- It is easy for machines to parse and generate. 

### What does JSON contain? 
- 1. A collection of key/value pairs. It can be realized as an object, a record, struct, dictionary, hash table, keyed list, or associative array. 
  Eg of an JSON Object 
  { "string" : "value" }

- 2. An ordered list of values. This can be realized as an array, vector, list, or sequence. 
  Eg of an JSON Array
  [value,...]
  
### JSON Uses 
- JSON has become extremely popular. 
- It is used for data for all kinds of applications. 
- It is the most popular way of sending data for web APIs. 

### Basic Data Types
- Strings: text enclosed in single or double quotation marks. 
- Numbers: integer or decimal, positive or negative without quotes. 

### Simple JSON Example 
    Eg. 1 JSON with key value pairs alone - 
    {
      "location": "trivandrum"
      "temperature": 35.5
    }
    
    Eg. 2 JSON with JSON array - 
    {
      "person" :[
          "name": "Tom", 
          "age": 28, 
          "employed": true, 
          "height": 6.5 
      ]
    }
    
    Eg 3 JSON with nested elements - 
    [
    {
        "header": "File",
        "items": [
            {
                "id": "Open",
                "label": "Open"
            },
            {
                "id": "New",
                "label": "New"
            },
            {
                "id": "Close",
                "label": "Close"
            }
        ]
    },
    {
        "header": "View",
        "items": [
            {
                "id": "ZoomIn",
                "label": "Zoom In"
            },
            {
                "id": "ZoomOut",
                "label": "Zoom Out"
            },
            {
                "id": "OriginalView",
                "label": "Original View"
            }
        ]
      }
    ]



