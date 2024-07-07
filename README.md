# web-scraping
**Overview**

This project contains a Python script to fetch and validate data files from multiple GitHub repositories. It is designed to scrape repositories for CSV and XLSX files, validate their contents against a specified format, and summarize the findings in a CSV report.


**Script Details**

**Fetch Repository Content**:
The fetch_repo_content(repo_url) function fetches the content of a given repository URL. It uses the requests library to make an HTTP GET request and parses the response content with BeautifulSoup.


**Parse HTML Content**:
The parse_repo_content(soup, base_url) function parses the HTML content of the repository page to extract file URLs and subdirectories. It looks for links with the class Link--primary.


**Validate Data Files**:
The validate_data_file(file_url, sample_df) function validates CSV and XLSX files against the sample format specified in submission_format.csv. It checks if the required columns (respondent_id, xyz_vaccine or h1n1_vaccine, and seasonal_vaccine) are present and consistent.


**Process Repositories**:
The process_repositories(repo_urls, sample_df) function processes each repository URL to identify valid submission files. It summarizes the results, indicating whether valid submissions were found, the repository visibility, and the most recent valid submission URL.


**Input Files**: 
_links_of_submission.xlsx_: Contains GitHub repository URLs.
_submission_format.csv_: Specifies the format criteria for data files.


**Output File**: 
_submission_results.csv_: Summarizes the findings for each repository.


**Here's an overview of the columns in the output DataFrame:**

_Repository URL_: The URL of the GitHub repository being evaluated.

_Submission Status_: Indicates whether a valid submission was found or not.

_Repository Visibility_: States if the repository is Public or Private.

_Submission in Root Dir_: Indicates if the valid submission is located in the root directory of the repository.

_Most Recent Valid Submission URL_: The URL of the most recent valid submission found in the repository.

