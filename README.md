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

### What are the APIs available for reading or writing JSON? 
- Java doesn't have any inbuilt APIs. However, there are many APIs like json-simple-1.1.1.jar, java-json.jar, javax.json.jar. 

### Explain below JSON structure below. 
    {
        "firstName": "Tom", 
        "lastName": "John", 
        "age": 45, 
        "fullTime": true
    }

    {
      "Employees": [
          {
          "name": "abc", 
          "designation": "HR Executive", 
          "pay": 5000
          "contacts": [
            {
            "landline": "100-2123-1232", 
            "mobile": "8989-90909"
            }
          ]
          },
          {
           "name": "xyz", 
          "designation": "Officer", 
          "pay": 5000
          "contacts": [
            {
            "landline": "3940-2123-1232", 
            "mobile": "231-322"
            }
          ]
          }
      ]
    }
  
    In JSON {} reprents JSON Object while [] represents JSON array.  
  
  Explanation: 
                
| Element  | Description | Type | Notes |
| -------- | ----------- | ---- |------ |
| firstName| First name  |Sting |       |
| lastName | Last name   |Sting |       |
| age      | Age in yrs  |Number|       |
| fullTime | True if working full time; else false | Boolean | Full time 45 hours per week. |

### Explain below JSON.
- Most JSON has nesting. 
- Objects may include arrays, other objects and so on. 
  
Employee eg. 

      {
        "employee": [
                "firstName": "John", 
                "lastName": "Michael", 
                 "age": 43
        ] 
      }
      
 Song eg. 
 
      {
        "song": 
            {
              "title": "Song Title here", 
              "artist": "artist name here",
              "musicians": [
                  "AR Rehman", "KS Chitra"
              ]
            } 
      }
 
 | Element | Description | Type | Notes | 
 | --------| ----------- | -----| ------|
 | song    | Top level   | song data object | | 
 | &nbsp; &nbsp; title | Song title | string | | 
 | &nbsp; &nbsp; artist | Song artist | string | | 
 | &nbsp; &nbsp; musicians | A list of musicians that play on the song | array of string | | 
 


