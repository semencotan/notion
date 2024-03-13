# notion
import requests

# Define your Notion API key
api_key = "YOUR_NOTION_API_KEY"

# Define the URL to query a Notion database
database_id = "YOUR_NOTION_DATABASE_ID"
url = f"https://api.notion.com/v1/databases/{database_id}/query"

# Define headers with the necessary authorization and content type
headers = {
    "Authorization": f"Bearer {api_key}",
    "Content-Type": "application/json",
    "Notion-Version": "2021-05-13"  # Adjust this version as necessary
}

# Send a GET request to retrieve data from the Notion database
response = requests.get(url, headers=headers)

# Check if the request was successful
if response.status_code == 200:
    data = response.json()
    # Do something with the retrieved data
    print(data)
else:
    print(f"Error: {response.status_code} - {response.text}")
