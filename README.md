# ESA API Automation Script

## Overview

This Python script automates interactions with the Cisco Email Security Appliance (ESA) API, allowing users to:

Authenticate and retrieve a JWT token

Fetch available dictionaries

Add words to a specified dictionary

## Features

Base64 Encoding: Automatically encodes username and password.

Customizable Inputs: User-configurable ESA hostname, credentials, dictionary name, and words.

CSV-style Input for Words: Words can be provided in a simple comma-separated format.

Handles HTTP 200 & 201 as Success: Ensures API requests are validated correctly.

## Installation

Prerequisites

- Python 3.x
- requests library (install using pip install requests)

Setup

1. Clone the repository:
```
git clone https://github.com/your-repo/esa-api-script.git
cd esa-api-script
```
2. Install dependencies:
```
pip install -r requirements.txt
```
## Configuration

Modify the following variables in the script before running:
```
# ========== USER CONFIGURATION ==========
ESA_HOST = "x.x.x.x:6080"  # ESA Hostname/IP
USERNAME = "user"  # Plain-text username
PASSWORD = "password"  # Plain-text password
DICTIONARY_NAME = "mydictionary"  # Dictionary to update

WORDS_TO_ADD_CSV = "url1.com, testing.com"  # Comma-separated words
```
- ESA_HOST: The IP address or hostname of your ESA.
- USERNAME: ESA API username (will be Base64-encoded automatically).
- PASSWORD: ESA API password (will be Base64-encoded automatically).
- DICTIONARY_NAME: The name of the dictionary you want to update.
- WORDS_TO_ADD_CSV: Words to add in a comma-separated format.
  - Format: word or word:score:option (e.g., *credit:2:prefix).

## Usage

Run the script

Execute the script with:
```
python esa_api_script.py
```
Example Output
```
Attempting login with encoded credentials...
Login successful!
Successfully added words to MyDictionary
```
## Troubleshooting

Invalid Credentials

Ensure you have the correct username/password.

Manually verify Base64 encoding with:
```
echo -n "your-username" | base64
echo -n "your-password" | base64
```
Connection Issues

- Check network access to ESA_HOST.
- Verify ESA API service is running.

Debugging API Responses

If unexpected errors occur, inspect the API responses in the script output.

## License

This script is open-source and available under the MIT License.

Contributions

Feel free to submit pull requests or issues via GitHub.



