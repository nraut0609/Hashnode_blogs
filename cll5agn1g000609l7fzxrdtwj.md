---
title: "Deep Learning with Python for 
        ♾️DevOps Engineers♾️"
datePublished: Tue Jan 10 2023 15:35:31 GMT+0000 (Coordinated Universal Time)
cuid: cll5agn1g000609l7fzxrdtwj
slug: deep-learning-with-python-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691681625752/9e4795c3-db8d-4b5d-a20f-cd8f49d730d1.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691679759882/9766c7e4-ae36-4d33-85e4-a3088ab426ef.png
tags: python, python3, devops, python-beginner, devops-journey

---

## **Python Libraries:**

A Python library is a collection of related modules. It contains bundles of code that can be used repeatedly in different programs. It makes Python Programming simpler and more convenient for the programmer. As we don’t need to write the same code again and again for different programs.

*Some Python Libraries are as follows -*

**1\. numpy:** Provides numerical computing capabilities, including arrays, linear algebra, Fourier transforms, and more.

**2\. pandas:** Offers data manipulation and analysis tools, providing data structures like DataFrames for efficient data handling.

**3\. matplotlib:** A popular data visualization library for creating charts, plots, and graphs.

**4\. scikit-learn:** A machine learning library that provides tools for classification, regression, clustering, and more.

**5\. tensorflow and pytorch:** Deep learning frameworks that enable building and training neural networks for tasks like image recognition and natural language processing.

**6\. flask and Django:** Web development frameworks used to build scalable and dynamic web applications.

**7\. sqlalchemy**: A powerful and flexible ORM (Object-Relational Mapping) library for working with databases.

**8\. pytest and unittest:** Testing frameworks for writing and executing unit tests to ensure code quality and functionality.

**9\. requests:** A library for making HTTP requests, used for interacting with web APIs.

**10\. beautifulsoup and scrapy:** Libraries for web scraping and extracting data from HTML and XML documents.

---

**A**s a DevOps Engineer, you are correct that being able to parse various file formats, such as JSON and YAML, is an important skill. Python provides several libraries that can be used to handle these file formats. Let’s take a look at how to read JSON and YAML files in Python.

## **What is JSON?**

JSON (JavaScript Object Notation) is a lightweight data interchange format that is easy for humans to read and write and easy for machines to parse and generate. It is based on a subset of the JavaScript Programming Language, and it is often used to transmit data between a server and a web application, as an alternative to XML.

**Difference Between json.dump() and json.load()**

`json.dump()` is used to convert a Python object into a JSON string and write it to a file.

```python
import json
data = {"name": "John", "age": 30, "city": "New York"}
with open("data.json", "w") as file:
 json.dump(data, file)
```

`json.load()` is used to read a JSON string from a file and convert it back into a Python object.

```python
import json
with open("data.json", "r") as file:
 data = json.load(file)
print(data)
```

### Reading JSON in Python:

To read JSON files in Python, you can use the built-in `json` module. Here's an example of how to read a JSON file:

```python
import json
# Open the JSON file
with open('data.json', 'r') as file:
    # Load the JSON data
    data = json.load(file)
# Access the data
print(data)
```

## **What is YAML?**

YAML was previously known as "Yet another markup language." But now it is called "YAML ain't markup language."

It is not a programming language. It is a data format used to exchange data. It is similar to XML and JSON data types. YAML is a human-readable language that can be used to represent data.

### Reading YAML in Python:

To read YAML files in Python, you can use the `pyyaml` library. You can install it using `pip install pyyaml`. Here's an example of how to read a YAML file:

```python
import yaml
# Open the YAML file
with open('data.yaml', 'r') as file:
    # Load the YAML data
    data = yaml.safe_load(file)
# Access the data
print(data)
```

### Additional Libraries for DevOps Tasks:

In addition to `json` and `pyyaml`, there are several other Python libraries commonly used by DevOps Engineers. Some of these libraries include:

* `os`: Used for interacting with the operating system, such as working with files, directories, and environment variables.
    
* `sys`: Provides access to system-specific parameters and functions, allowing you to manipulate the Python runtime environment.
    
* `paramiko`: A library for SSH protocol implementation, allowing you to securely connect to remote servers and execute commands.
    
* `requests`: Used for making HTTP requests, making it useful for interacting with web APIs and services.
    
* `docker`: A library for interacting with Docker, enabling you to manage Docker containers and images programmatically.
    
* `ansible`: A powerful automation tool for configuration management, deployment, and orchestration.
    
* `terraform`: A library for interacting with Terraform, a tool for infrastructure provisioning and management.
    
    ## **Functions of YAML**
    
    * YAML (YAML Ain't Markup Language) is a human-readable data serialization format.
        
    * It is often used for configuration files, data exchange between languages, and other structured data representations.
        
    * YAML uses indentation and colons to represent hierarchical data structures.
        
    * It supports various data types, including strings, numbers, booleans, null, arrays (lists), and objects (mappings).
        
    * YAML allows for multiline strings, making it easy to represent long blocks of text.
        
    * YAML comments start with the `#` symbol and can be used to provide additional information or explanations.
        
    
    ## Functions of JSON
    
    * JSON is a data interchange format used to represent structured data as a string.
        
    * In Python, JSON is supported through the `json` module in the standard library.
        
    * The `json` module provides functions to work with JSON data in Python.
        
    * `json.dumps()`: This function is used to convert a Python object (e.g., dictionary, list) into a JSON-formatted string.
        
    * `json.loads()`: This function is used to parse a JSON-formatted string and convert it into a Python object (e.g., dictionary, list).
        
    * JSON keys must be strings, and the values can be strings, numbers, booleans, `None`, lists, or other JSON objects (dictionaries).
        

# **Tasks:**

**Task 1)** Create a Dictionary in Python and write it to a JSON file.

```python
import json
dict = { "Name" : "Radhey", "Age" : "24"}
json_object = json.dumps(dict, indent = 1)
print(json_object)
```

![](https://miro.medium.com/v2/resize:fit:847/1*81dU5MJzUsWa9jT0ZP14-Q.png align="left")

**Task 2)** Read a json file services.json kept in the folder and print the service names of every cloud service provider.

```python
services.json
{
  "aws": {
    "name": "ec2"
  },
  "azure": {
    "name": "VM"
  },
  "gcp": {
    "name": "compute engine"
  }
}
```

```python
import json
# Read the JSON file
with open(‘services.json’, ‘r’) as file:
 data = json.load(file)
# Extract service names for each cloud provider
for provider, services in data.items():
 service_name = services.get('name')
 print(f"{provider} : {service_name}")
```

![](https://miro.medium.com/v2/resize:fit:847/1*MCIeq0YUX_P98eSHfCFF_g.png align="left")

**Task 3)** Read the YAML file using Python, file services.yaml, and read the contents to convert yaml to json.

```python-repl
services.yaml
aws:
 name: ec2
azure:
 name: VM
gcp:
 name: compute engine
```

```python
import yaml
import json
# Read the YAML file
with open(‘services.yaml’, ‘r’) as file:
 data = yaml.safe_load(file)
# Convert YAML to JSON
json_data = json.dumps(data)
# Print the JSON data
print(json_data)
```

![](https://miro.medium.com/v2/resize:fit:847/1*Pa710-d-EqKN-Fkz_j74zQ.png align="left")

*Remember that YAML and JSON are not 100% equivalent in terms of features and syntax, so the conversion might not be perfect for all cases. However, for many common use cases, this approach should work well.*

### **Conclusion:🪂**

Python libraries are the backbone of efficient DevOps practices. By harnessing the power of `json`, `PyYAML`, and their seamless integration, DevOps engineers can smoothly handle JSON and YAML data, automate tasks, and enhance collaboration across teams. This dynamic duo empowers you to bridge the gap between data serialization formats and effortlessly convert between them, simplifying your DevOps journey.🚞