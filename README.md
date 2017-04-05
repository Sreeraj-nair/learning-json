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
 
Eg JSON for describing a menu. 

    [
      {
          "header": "File", 
          "items": [
              {
                  "id": "Open", 
                  "label": "Open"
              }
              {
                  "id": "New", 
                  "label": "New"
              }
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
              }
              {
                  "id": "ZoomOut", 
                  "label": "Zoom Out"
              }
              {
                  "id": "OriginalView", 
                  "label": "Original View"
              }
          ]     
      }
    ]
    
| Element | Description | Type | Notes | 
| --------| ------------| -----| ------| 
| Top level | Menu columns | array of menu column objects | | 
| &nbsp; &nbsp; header | Name of the column | string | | 
| &nbsp; &nbsp; items | list of menu items under the column | array of menu items | | 
| &nbsp; &nbsp; &nbsp; id | id of menu item | string | | 
| &nbsp; &nbsp; &nbsp; label | id of menu item that is displayed in the UI | string | | 

### Java code to read JSON file. 
- Download JSON.simple » 1.1.1 from maven repository and add it to the eclipse library. 
- Below is the code snippet to read values from a JSON file. 
      
      import java.io.FileInputStream;
      import java.io.InputStreamReader;
      import java.util.Iterator;
      import org.json.simple.JSONArray;
      import org.json.simple.JSONObject;
      import org.json.simple.parser.JSONParser;
      
      public class ReadJSONFromFile{ 
          public static void main(String args[]){ 
              JSONParser parser = new JSONParser(); 
              
              try{
                  // get current working directory 
                  String currentWorkingDirectory = System.getProperty("user.dir"); 
                  System.out.println(currentWorkingDirectory);
                  
                  // read JSON file and parse the content in it
                  JSONObject  rootJSONObject = (JSONObject)parser.parse(new InputStreamReader(new 
		  FileInputStream("D:\\Song.json")));	
                  
                  // read JSONObject Song as JSONObject 
                  JSONObject songObj = (JSONObject)rootJSONObject.get("song"); 
                  System.out.println("Song obj: " +songObj);
                  
                  // convert the rootJSONObject to JSONString and store it as String
                  String jsonObject = rootJSONObject.toJSONString(); 
			            System.out.println("JSON Object: "+jsonObject);
                  
                  // other way of doing it
                  String songObject = rootJSONObject.get("song").toString();  
			            System.out.println("Song Object: "+songObject);
                   
                  // get artist
                  String artist = songObj.get("artist").toString(); 
			            System.out.println("Artist: "+artist);
			            
                  // get title 
			            String title = songObj.get("title").toString(); 
			            System.out.println("Title: "+title);
	              
                 // get hold of JSONArray
	               JSONArray msg = (JSONArray) songObj.get("musicians");
	               System.out.println("Msg: "+msg.toString());
	               
                 // iterate through the JSONArray
	               Iterator<?> i = msg.iterator(); 
	                 while(i.hasNext()){
	            	   System.out.println(i.next());
	                 }
              }
              catch(Exception ex){ 
                  ex.printStackTrace(); 
              }
          }
      }
      
### Another eg of nested or multi-level JSON. 

	package com.nestedJson;
	import java.io.FileInputStream;
	import java.io.InputStreamReader;
	import org.json.simple.JSONArray;
	import org.json.simple.JSONObject;
	import org.json.simple.parser.JSONParser;

	public class ReadNestedJSON {
	
		public static void main(String args[]){
		 	JSONParser parser = new JSONParser();

			try{
			   	//JSONObject  root = (JSONObject)parser.parse(new InputStreamReader(new 							FileInputStream("D:\\Nested.json")));		
			   
			   	// Get JSON array from the file 
			   	JSONArray array = (JSONArray)parser.parse(new InputStreamReader(new 								FileInputStream("D:\\Nested.json")));
			   	System.out.println("Root JSON Object: "+array);
			   
			   	// Get length of the JSONArray
			   	int arrayLength = array.size(); 
			   	System.out.println("JSON Array Lenght: "+arrayLength);
			   
			   	// Get first JSON Object from the array
			   	JSONObject object1 = (JSONObject)array.get(0); 
			   	System.out.println("Object One: "+object1);
			   
			   	// Get second JSON Object from the array
			   	JSONObject object2 = (JSONObject)array.get(1);
			   	System.out.println("Object One: "+object2);
			   
			   	// Get JSON Object header 
			   	String header1 = (String)object1.get("header"); 
			   	//String headerString = header.toJSONString();
			   	System.out.println("First Header: "+header1);
			   
			   	// Get items array
			   	JSONArray items1 = (JSONArray)object1.get("items"); 
			   	System.out.println("Items: "+items1);
			   
				// Get items array size
				int items1ArraySize = items1.size(); 
				System.out.println("Items Array: " +items1ArraySize);

				// Get first JSON Object from Items array
				JSONObject firstObjectInsideItems = (JSONObject) items1.get(0);
				System.out.println("First object within Items: "+firstObjectInsideItems);

				// Get id from first 
				String id = (String) firstObjectInsideItems.get("id"); 
				System.out.println("ID: "+id);

				String label = (String)firstObjectInsideItems.get("label"); 
				System.out.println("Label: "+label);
			}
			catch(Exception ex){
				ex.printStackTrace();
			}
		}

	}

