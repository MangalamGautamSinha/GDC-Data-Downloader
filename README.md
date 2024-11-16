# File Download and Organization Script for Cancer Genomics Data

This repository contains a Python script implemented in a Jupyter notebook for downloading genomic data files from the GDC (Genomic Data Commons) portal using file UUIDs. The script organizes the downloaded files into directories based on their associated subtypes.

## Features
- Reads file UUIDs and subtypes from a CSV file.
- Downloads data files from the GDC API.
- Automatically organizes downloaded files into directories named after their subtypes.

## Getting Started

### Prerequisites
Ensure the following are installed:
- Python 3.8 or above
- Required Python libraries:
  - `pandas`
  - `requests`
  - `os`

You can install the libraries with:
```bash
pip install pandas requests
```

### Usage
1. **Input CSV File**:
   - The input CSV file (`Initial_TNBC_FileUUID_Subtype.csv`) should have two columns:
     - `File_UUID`: The unique identifier for the file to download.
     - `Subtype`: The subtype category for organizing the file.

2. **Run the Script**:
   - The script fetches data for each file UUID and saves it into a directory corresponding to its subtype.
   - Example file structure after running:
     ```
     ./Basal/
         <file_uuid_1>.tsv
         <file_uuid_2>.tsv
     ./Luminal/
         <file_uuid_3>.tsv
     ```

3. **Execute in Jupyter Notebook**:
   - Open the notebook containing this script.
   - Update the `input_file_name` variable if your CSV file has a different name.
   - Run the notebook cells sequentially.

### Output
- A directory for each subtype is created if it doesn’t already exist.
- Downloaded files are saved in the appropriate subtype directory.

## Error Handling
- The script handles download errors with a simple try-except block and logs failed downloads with an error message.
