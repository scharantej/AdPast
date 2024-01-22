## Python Flask Application Design for Google Ads Change History Evaluation

### HTML Files

- **index.html**:
  - Serves as the home page of the application.
  - Facilitates user interaction (e.g., selecting an ad campaign, date range) to initiate the change history evaluation process.
  - Contains necessary elements to display the campaign information and change history results.
- **change_history.html**:
  - Presents the results of the change history evaluation, including detailed information about the changes made to the ad campaign within the specified date range.
  - Displays metrics such as modified attributes, timestamps, and user who made the changes.
  - Provides options for exporting the data to a user-friendly format (e.g., CSV, Excel).

### Routes

- **Homepage**:
  - URL: `/`
  - HTTP Method: `GET`
  - Purpose: Displays the home page (`index.html`) where users can select the campaign and date range for change history evaluation.
- **Change History Evaluation**:
  - URL: `/change_history`
  - HTTP Method: `POST`
  - Purpose: Accepts user input from the home page and generates the change history report.
  - Functionality:
    - Extracts the selected campaign and date range from the request data.
    - Queries the Google Ads API to retrieve the change history for the specified campaign and date range.
    - Stores the retrieved data in a structured format (e.g., Pandas DataFrame) for easy presentation.
    - Renders the `change_history.html` template, passing the change history data for display to the user.
- **Export Data**:
  - URL: `/export_data`
  - HTTP Method: `POST`
  - Purpose: Initiates the export of change history data in the specified format (CSV, Excel, etc.).
  - Functionality:
    - Accepts the desired export format as part of the request.
    - Converts the structured change history data into the selected format.
    - Generates a downloadable file containing the exported data.
    - Returns a response with the file attached for download by the user.