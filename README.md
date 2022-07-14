# snow_api

```
#Need to install requests package for python
#easy_install requests
import requests

# Set the request parameters
url = 'https://dev72453.service-now.com/api/now/table/incident?sysparm_query=sys_updated_on%3E%3Djavascript%3Ags.dateGenerate('2022-07-12'%2C'00%3A00%3A00')%5Esys_updated_on%3Cjavascript%3Ags.dateGenerate('2022-07-13'%2C'00%3A00%3A00')&sysparm_display_value=true&sysparm_exclude_reference_link=true&sysparm_limit=1'

# Eg. User name="admin", Password="admin" for this code sample.
user = 'admin'
pwd = 'admin'

# Set proper headers
headers = {"Content-Type":"application/json","Accept":"application/json"}

# Do the HTTP request
response = requests.get(url, auth=(user, pwd), headers=headers )

# Check for HTTP codes other than 200
if response.status_code != 200: 
    print('Status:', response.status_code, 'Headers:', response.headers, 'Error Response:',response.json())
    exit()

# Decode the JSON response into a dictionary and use the data
data = response.json()
print(data)

```
