# GitHub-Python-Jira

# Automated Jira Story Creation from GitHub Issues

This project is a Flask application that automates the creation of Jira stories when comments are made on GitHub repository issues. It uses the [`requests`](http://docs.python-requests.org) library to interact with the Jira API and create issues based on the provided payload.

## Features

- Automates the creation of Jira stories from GitHub issue comments.
- Uses [Flask](https://flask.palletsprojects.com/) to handle HTTP requests.
- Interacts with Jira API using the [`requests`](http://docs.python-requests.org) library.
- Supports JSON payloads for Jira issue creation.

## Prerequisites

- Python 3.6 or higher
- Jira account with API access
- Flask library
- `requests` library

## Installation

**Clone the repository:**

   ```sh
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name
   ```

## Usage

**Run the Flask application:**

   ```sh
   python app.py

   ```

**Send a POST request to create a Jira story:** You can use tools like curl, Postman, or any HTTP client to send a POST request to the `/createJira` endpoint. Example using curl:

   ```sh
   curl -X POST http://localhost:5000/createJira -H "Content-Type: application/json" -d '{
    "fields": {
        "description": {
            "content": [
                {
                    "content": [
                        {
                            "text": "Order entry fails when selecting supplier.",
                            "type": "text"
                        }
                    ],
                    "type": "paragraph"
                }
            ],
            "type": "doc",
            "version": 1
        },
        "project": {
            "key": "SCRUM"
        },
        "issuetype": {
            "id": "10003"
        },
        "summary": "Main order flow broken"
    },
    "update": {}
}'


   ```

## Configuration

- Jira API URL: The URL for the Jira API endpoint is set to https://veerarakesh56.atlassian.net/rest/api/3/issue.
- Set up your Jira API token and email_id: Replace the API_TOKEN and email_id placeholders in the code with your actual Jira API token and email_id.
- Authentication: Basic authentication is used with an email and API token.
- Headers: The request headers include Accept: application/json and Content-Type: application/json.

