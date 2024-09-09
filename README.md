# Google Sheets to CSV Script

This Python script fetches data from a Google Spreadsheet and saves it as a CSV file. The script uses Google Sheets API to retrieve data and handles OAuth2 authentication to access the Google Sheet. 

## Prerequisites

Before running the script, ensure you have the following:

1. **Python 3.x**: Make sure Python is installed on your system. You can download it from [python.org](https://www.python.org/downloads/).
2. **Google Cloud Project & API Access**: You need a Google Cloud project with the Google Sheets API enabled. Follow the steps below to set this up.

## Setup

### Step 1: Enable Google Sheets API and Download Credentials

1. Go to the [Google Cloud Console](https://console.developers.google.com/).
2. Create a new project or use an existing one.
3. Enable the **Google Sheets API** for your project by navigating to **APIs & Services** > **Library**, then searching for and enabling the Google Sheets API.
4. Navigate to **APIs & Services** > **Credentials** and create credentials for an **OAuth 2.0 Client ID**.
5. Download the `credentials.json` file from your Google Cloud project and save it in the root directory of this project.

### Step 2: Install Required Python Packages

The script uses several Python packages. Install these packages by running the following command:

```bash
pip install --upgrade google-auth google-auth-oauthlib google-auth-httplib2 google-api-python-client
```

You also need the `csv` module, which is included by default in Python.

### Step 3: Update the Script with Spreadsheet ID

In the script, replace the `SPREADSHEET_ID` variable with the ID of the Google Spreadsheet you want to fetch data from. 

To find your spreadsheet ID:
1. Open the Google Spreadsheet in your browser.
2. The ID is the long string between `/d/` and `/edit` in the URL. 
   Example: For the URL `https://docs.google.com/spreadsheets/d/1XHkLkGsXIlpYJxCXpnDrhDgp5vq1MvolFyu03iaVxBA/edit`, the `SPREADSHEET_ID` is `1XHkLkGsXIlpYJxCXpnDrhDgp5vq1MvolFyu03iaVxBA`.

### Step 4: Run the Script

To run the script, use the following command:

```bash
python script_name.py
```

When you run the script for the first time, it will open a browser window for you to authenticate with your Google account. This will allow the script to access your Google Sheets data.

A file called `token.json` will be created after authentication, which stores your credentials for future runs. The script will use this file to avoid requiring authentication each time.

### Step 5: View the Output

Once the script is executed successfully:
- It will print the rows from the Google Sheet to the console.
- It will create an `output.csv` file in the root directory of your project containing the data retrieved from the Google Spreadsheet.

### Error Handling

If the script encounters an error (e.g., network issues or permission problems), it will catch the error and print the exception message.

## License

This project is licensed under the MIT License.

---

### Additional Notes

- The script fetches data from the range `A1:Z114` in `Sheet1`. You can modify the range and sheet name in the script to fetch data from a different range or sheet.
- Ensure that your Google Spreadsheet's sharing settings allow your authenticated Google account to view the spreadsheet data. If it's private, you will need to share the sheet with the account you use for authentication.

---

This README file provides a step-by-step guide on setting up the project, installing dependencies, and running the script. You can adjust it further based on any additional configurations or features you add to the script.
