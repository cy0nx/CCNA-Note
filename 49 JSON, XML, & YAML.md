## JSON  

● **JSON** (JavaScript Object Notation) is an open standard file format and data interchange format that uses human-readable text to store and transmit data objects.  
● It is standardized in RFC 8259.

● It was derived from JavaScript, but it is language-independent and many modern programming languages are able to generate and read JSON data.  
→REST APIs often use JSON.

● Whitespace is insignificant.

● JSON can represent four ‘primitive’ data types:  
→string  
→number  
→boolean  
→null

● JSON also has two ‘structured’ data types:  
→object  
→array  
<br>


###  JSON structured data types:  

● An **object** is an unordered list of key-value pairs (variables).  
→Objects are surrounded by curly brackets {} .  
→The key is a string.  
→The value is any valid JSON data type (string, number, boolean, null, object, array).  
→The key and value are separated by a colon : .  
→If there are multiple key-value pairs, each pair is separated by a comma.  
![1445-08-10 03_44_16-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d5fc5ee9-c66b-4580-a71c-f88e27412849)  
![1445-08-10 03_44_47-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/adb904bb-2d14-44ce-8df5-d7c47fe68415)  
<br>


● An **object** is an unordered list of key-value pairs (variables).

● An **array** is a series of values separated by commas.  
→not key-value pairs.  
→the values don’t have to be the same data type.  
![1445-08-10 03_46_22-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/88d64869-4f15-4a46-87cc-8e41da49a678)  
![1445-08-10 03_46_54-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/ca57eb01-1e32-4b0b-81f4-f3aa064b606c)  
<br>  


##  XML  

● **XML** (Extensible Markup Language) was developed as a markup language, but is now used as a general data serialization language.  
→markup languages (ie. HTML) are used to format text (font, size, color, headings, etc.)

● XML is generally less human-readable than JSON.

● Whitespace is insignificant.

● Often used by REST APIs.

● <key>value</key>  
![1445-08-10 03_48_13-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/fac24ce1-e64f-4a72-a6a1-e31d3c4d3d99)  
![1445-08-10 03_49_28-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/341542ba-a604-483a-b05b-1e25030a6834)  
<br>  


##  YAML  

● **YAML** originally meant Yet Another Markup Language, but to distinguish its purpose as a dataserialization language rather than a markup language, it was repurposed to YAML Aint Markup Language.

● YAML is used by the network automation tool Ansible (we’ll cover that later!).

● YAML is very human-readable.

● Whitespace **is significant (unlike JSON and XML)**.  
→Indentation is very important.

● YAML files start with --- .

● - is used to indicate a list.

● Keys and values are represented as key:value.  
![1445-08-10 03_51_03-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/f733fdeb-1436-4f53-8c1c-31183ce08bf8)  
<br>

![1445-08-10 03_51_21-Day 60 Slides - JSON, XML, YAML pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/5a8a2d9a-1b87-45ed-8acd-2b14c201bf49)

