### Python API


<img width="566" alt="api" src="https://user-images.githubusercontent.com/110182832/183614815-a17bac2b-e6e2-4ee5-9814-08b16948384b.png">



````
import requests

response = requests.get("https://www.bbc.co.uk/news")
print(response)
````
<<<<<<< HEAD


import requests

response = requests.get("https://www.bbc.co.uk/news")
### API call to bbc to get response


#print(response)


### if the web page is live welcome the user with the status
#or print a message OOPs something went wrong

if response.status_code == 200: #if this is true execute next line

    print(f"The status code is {response.status_code} the website is live") # should give us the status only - numbers 200-404 -501 etc

else:
    print(f"Oops it's not working, error code {response.status_code} ")

### second iteration
````
import requests

response = requests.get("https://www.bbc.co.uk/nes")
if response:  # what is it checking
    print("success")
elif response:  # what is it checking
    print("unsuccessfull")

else:  # what is it checking
    print(f"OOps something went wrong please try later, the status code is {response.status_code}")
````

### Third iteration
### create a function that returns the status code with appropriate message
### Use control flow to make the right decision
### use RETURN not print inside your function

````
import requests

response = requests.get("https://www.bbc.co.uk/news")

def status_function():

    if response.status_code == 200:
        return f"Go and visit the website, status code is {response.status_code}"

    else:
        return f"something went wrong, error code is {response.status_code}"

print(status_function())
````

````
###  import required package
import requests
### valid post code or invalid  - url of the API
url = "http://api.postcodes.io/postcodes/"

### store the data

postcode = "BL15GY"
url_arg = url + postcode  # "http://api.postcodes.io/postcodes/BL1 5GY"



### display the outcome
response = requests.get(url_arg)
print(response.status_code)
#print(type(response.json()))

response_dict = response.json()

result_dict = response_dict["result"]
for key in result_dict.keys():
    if key == "postcode":
        print(f"please confirm this is your postcode {}")
    print(key)

#print(result_dict)
#print(response_dict)

### please print the post code
### print(response_dict["postcode"])
````


### Get postcode and longitude & latitude of that postcode

````
###  import required package
import requests

### valid post code or invalid  - url of the API
url = "http://api.postcodes.io/postcodes/"

### store the data

postcode = "BL15GY"
url_arg = url + postcode  # "http://api.postcodes.io/postcodes/BL1 5GY"



### display the outcome
response = requests.get(url_arg)
print(response.status_code)
### print(type(response.json()))

response_dict = response.json()

result_dict = response_dict["result"]
for key in result_dict.keys():
    if key == "postcode":
        print(f"please confirm this is your postcode {result_dict['postcode']}")   # enter key/value that would print the postcode

    elif key == "longitude":
        print(f"This is your longitude {result_dict['longitude']}")

    elif key == "latitude":
        print(f"This is your latitude {result_dict['latitude']}")
    #print(key)

print(result_dict)
### print(response_dict)
### please print the post code
### print(response_dict["postcode"])


### display url together with given postcode

### check the type of data scrapped from the web - response
### convert data type if needed to iterate through the data and print required information
### display longitude - latitude - postcode etc
````

````
import requests


url = "http://api.postcodes.io/postcodes/"

postcode = "BL15GY"
url_arg = url + postcode  # "http://api.postcodes.io/postcodes/BL1 5GY"

response = requests.get(url_arg)

response_dict = response.json()

# print(response_dict)
result_dict = response_dict["result"]
print(result_dict)
def post_code():
    if key == "postcode":
      return f"your postcode is {response_dict['postcode']}"

print(post_code())
````
=======

