# AI-Model-Comparison

The raw output from each model is shown below the model name. llstudio.ai was used to generate each response. There was no system prompt. All formatting was done by the models themselves

## Write a simple Python script that requests a webpage and returns the results.

### TheBloke • codellama instruct 7B q4_k_s gguf

```
import requests

url = "https://www.example.com"
response = requests.get(url)

print(response.text)
```
This script uses the `requests` library to make an HTTP GET request to the specified URL, and then prints the response text to the console. The `response.text` attribute contains the HTML content of the webpage, which can be parsed using various libraries or methods as needed.


### TheBloke • wizardcoder python v1 0 13B q4_k_s gguf

"""

import urllib.request

url = input("Enter URL: ")

response = urllib.request.urlopen(url)

print(response.read()) 


### TheBloke • mistral instruct v0 1 7B q4_k_s gguf

 ```python
import requests
from bs4 import BeautifulSoup

url = input("Enter the URL: ")
response = requests.get(url)
soup = BeautifulSoup(response.text, 'html.parser')

print("\nResults:")
for i in range(1, 6):
    print(f"{i}. {soup.find('h' + str(i)).text}")
```


### TheBloke • zephyr beta 7B q4_k_s gguf

Here's a simple Python script that uses the built-in `urllib.request` module to request a webpage and return its contents:

```python
import urllib.request

# URL of the webpage you want to request
url = "https://www.example.com"

# Use the urlopen() function to open the URL and read its contents
response = urllib.request.urlopen(url)

# Read the response data as a byte stream
data = response.read()

# Close the response object to free up system resources
response.close()

# Print the contents of the webpage
print(data.decode())
```

This script first imports the `urllib.request` module, which provides functions for handling URLs and making HTTP requests. It then defines the URL of the webpage you want to request (in this case, "https://www.example.com"), and uses the `urlopen()` function to open the URL and read its contents as a byte stream. The script then decodes the byte stream into a string using the `decode()` method, prints it out, and finally closes the response object to free up system resources.


### TheBloke • stablelm zephyr 3B q4_k_s gguf

Here is a simple Python script using the requests library to request a webpage:

```python
import requests

def get_webpage(url):
    response = requests.get(url)

    if response.status_code == 200: # successful request
        return response.text
    else:
        return "Failed to retrieve page"

# replace with your desired URL
url = 'https://www.example.com'
print(get_webpage(url))
```

This script will send a GET request to the specified URL and return the HTML content of the webpage if the request is successful. If the request fails for some reason, it will return a failure message instead.

Please make sure that you have the `requests` library installed in your Python environment. You can install it using pip:

```bash
pip install requests
```


### TheBloke • openhermes 2 5 mistral 7B q4_k_s gguf

import requests

from bs4 import BeautifulSoup


url = 'https://www.example.com'

response = requests.get(url)

content = response.text

soup = BeautifulSoup(content, 'html.parser')

results = soup.find_all()

print(results)


### TheBloke • deepseek coder 6 instruct 7B q4_k_s gguf

Sure, here is an example of how you can do this using `requests` library in python:

```python
import requests

def get_webpage(url):
    response = requests.get(url)
    
    if response.status_code == 200:
        return response.text
    else:
        return "Failed to retrieve webpage"
        
print(get_webpage('https://www.example.com'))  # replace with your URL
```
This script sends a GET request to the specified URL and returns the content of the requested page if it is accessible. If not, it will print an error message indicating that the webpage could not be retrieved.

Please note: you need to have `requests` library installed in your python environment. You can install it using pip by running `pip install requests` command on your terminal or command prompt. 

Also, please make sure that you are allowed to scrape the webpage as per its terms of service. Some websites explicitly forbid this kind of activity and may block your IP if you attempt to do so frequently. Always respect website owners' rights and policies.


### TheBloke • nexusraven v2 13B q4_k_s gguf

The `requests` library is a powerful tool for making HTTP requests in Python. It allows you to easily send GET, POST, PUT, DELETE, etc. requests to web servers and parse the responses.

Here's an example of how to use it to request a webpage and return the results:
```python
import requests

url = 'https://www.example.com/'
response = requests.get(url)
print(response.text)
```
This code will send a GET request to the specified URL, and then print the response text (which is the HTML content of the webpage).

You can also use other methods like `post`, `put`, `delete` etc. depending on your requirement.


### phi-2.Q4_K_S.gguf

 import requests
 
response = requests.get('https://www.example.com')

print(response.text)


### NousResearch • Hermes 2 Pro Mistral 7B q4_0 gguf

import requests



url = 'https://www.example.com'  # Replace with the desired URL

response = requests.get(url)



if response.status_code == 200:

  print('Successfully fetched the webpage.')

  print('Content:', response.content)

else:

  print('Error:', response.status_code, 'while fetching the webpage.')


### lmstudio-ai • gemma it 2B q8_0 gguf

```python
import requests

# Define the URL of the webpage
url = "example.com"

# Make a GET request to the URL
response = requests.get(url)

# Check if the request was successful
if response.status_code == 200:
    # Parse the HTML content of the webpage
    html_content = response.text

    # Print the HTML content
    print(html_content)
else:
    # Handle error
    print("Error getting page content.")
```

**Example Usage:**

1. Replace `example.com` with the actual URL of the webpage you want to request.
2. Run the script.

**Output (assuming the webpage is accessible):**

```html
<!DOCTYPE html>
<html>
<head>...</head>
<body>...</body>
</html>
```

**Notes:**

* The `requests` library requires the `requests` package to be installed. You can install it with the following command: `pip install requests`.
* The `response.status_code` variable will indicate the status of the request, such as 200 for successful retrieval or 404 for not found.
* The `html_content` variable will contain the HTML content of the webpage.
* You can use the `Beautiful Soup` library instead of directly parsing the HTML string.


### Qwen • qwen chat q5 k m 7B 1_5 gguf

Sure, here's a simple Python script using the `requests` library to fetch the HTML content of a webpage and print it:

```python
import requests

# Replace 'https://example.com' with the URL you want to fetch
url = 'https://example.com'

# Send a GET request to the website
response = requests.get(url)

# Check if the request was successful (status code 200)
if response.status_code == 200:
    # Get the HTML content and print it
    webpage_content = response.text
    print(webpage_content)
else:
    print(f"Failed to fetch the page. Status code: {response.status_code}")
```

Make sure you have the `requests` library installed by running `pip install requests` if you haven't already. Replace `'https://example.com'` with the URL of the webpage you want to fetch.

This script will send a GET request to the specified URL, and if the request is successful (status code 200), it will print the HTML content of the webpage. If there's an error, it will display a message indicating that the page failed to fetch.


### bartowski • Starling LM beta I 7B q4_xs gguf

 Certainly! Below is a simple Python script using the `requests` library to request a webpage and print its content:

```python
import requests

# The URL of the webpage you want to request
url = 'https://example.com'

# Send a GET request to the specified URL
response = requests.get(url)

# Check if the request was successful (status code 200)
if response.status_code == 200:
    # Print the content of the webpage
    print(response.text)
else:
    # Print an error message if the request failed
    print(f'Failed to retrieve webpage: {response.status_code}')
```

Before running this script, make sure you have the `requests` library installed in your Python environment. You can install it using pip:

```bash
pip install requests
```

Replace `https://example.com` with the URL of the webpage you want to request. The script will print the content of the requested webpage if the request is successful, or an error message if the request fails.


### bartowski • stable code instruct 3B q8_0 gguf

Here's a simple Python script using the `requests` library to fetch a webpage and return the results:

```python
import requests

def get_webpage(url):
    try:
        response = requests.get(url)
        response.raise_for_status()

        return response.text

    except requests.exceptions.RequestException as err:
        print(f"Error requesting URL {url}: {err}")
        return None

    except Exception as e:
        print(f"An unexpected error occurred: {e}")
        return None

if __name__ == "__main__":
    url = input("Enter the URL to fetch: ")
    content = get_webpage(url)

    if content is not None:
        print("\nContent of the webpage:")
        print(content)
```

To use this script, you need to have the `requests` library installed. You can install it using pip:

```
pip install requests
```

After installing the required library, save the provided code in a file named `webpage_fetcher.py`. Then, run the script by executing the following command in your terminal or command prompt:

```
python webpage_fetcher.py
```

The script will then ask you to enter the URL of the webpage you want to fetch. After entering the URL, the script will display the content of the fetched webpage.


### TheBloke • mistral instruct v0 2 7B q4_k_s gguf

 To write a simple Python script that requests a webpage and returns the results, you can use the `urllib` library which comes built-in with Python. Here's an example of how to do this:

```python
import urllib.request

# Define the URL of the webpage you want to request
url = "https://www.example.com"

# Use the urlopen() function from urllib to open the connection to the server
# and read the response data
response = urllib.request.urlopen(url)

# Read all the data from the response object and decode it into a string
data = response.read().decode()

# Print the data to the console
print(data)

# Always remember to close the connection when you're done
response.close()
```

This script defines the URL of the webpage, opens a connection to the server using `urlopen()`, reads the response data into a string, and then prints the data to the console. Don't forget to close the connection when you're done!

Keep in mind that some websites may not allow their content to be scraped or accessed programmatically, so always make sure you have permission before attempting to request webpages using scripts like this one.
