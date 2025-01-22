# Postman API Testing Collection

This repository contains a Postman collection for API testing and automation. It includes all necessary requests, examples, and testing scripts for CRUD operations.

## Overview
- **Collection Name**: API_Automation_PositiveTests
- **Requests Included**:
  - `POST` - AddPlace
  - `GET` - GetPlace
  - `PUT` - UpdatePlace
  - `DELETE` - DeletePlace

## Prerequisites
1. Install [Node.js](https://nodejs.org/) (LTS version recommended).
2. Install [Newman](from commandline i.e., npm install -g newman) for running Postman collections from the command line.
3. Install Jenkins for continuous integration.

---

## Steps to Export and Use the Collection

### Step 1: Export the Postman Collection
1. Open Postman.
2. Go to **Collections** and export (e.g., `API_Automation_PositiveTests`).
3. Choose the **Collection v2.1** format.
4. Save the exported `.json` file to the local system.

### Step 2: Upload the Collection to GitHub
1. Go to  GitHub repository.
2. Click **Add file > Upload files**.
3. Upload the exported Postman collection `.json` file.
4. Commit the changes to the repository.

---

## Run Newman commands in Jenkins

### Step 3: Install Newman
1. Open a terminal.
2. Run the following command:
   npm install -g newman
   
### Step 4: Install Jenkins and set up project:

1.Download and install Jenkins from the official website.
2.Start the Jenkins server and access it via localbrowser (default: http://localhost:8080).
3.Clone the collection JSON file from GitHub:
4.Configure Jenkins job to pull the following files from  GitHub repository:
5.Collection Name: API_Automation_PositiveTests.postman_collection.json
6.Data File: postman_fuzz_test_data.csv
7.Add Newman commands in the Jenkins build configuration:
8.In the Build section of the Jenkins job, select Execute Windows batch command.
Add the following Newman command to run the collection:

//*  newman run API_Automation_PositiveTests.postman_collection.json ^
    -d postman_fuzz_test_data.csv ^
    --reporters cli,html ^
    --reporter-html-export newman-report.html *//
    
### Step 5: Performance testing conducted as part of this automation includes:

Spike Load, Fixed Load, Peak Load, and Ramp-Up Load Testing.
Test results are available in the form of HTML and PDF reports for reference.

   

