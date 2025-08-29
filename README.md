# PAN Card Number Validation Project

## 📜 Overview

This project focuses on the data cleaning and validation of Indian Permanent Account Numbers (PAN). The primary objective is to process a given dataset, identify valid and invalid PANs based on a set of predefined rules, and generate a summary report.

The script performs the following key tasks:
- **Data Cleaning**: Handles missing values, removes duplicates, and standardizes the data by trimming whitespace and converting to uppercase.
- **Format Validation**: Checks each PAN against specific structural and logical rules.
- **Categorization**: Classifies each PAN as 'Valid' or 'Invalid'.
- **Reporting**: Generates a final Excel file with the validation status for each PAN and a summary of the results.

---

## 🛠️ Technology Stack

- **Language**: Python
- **Libraries**: Pandas, re (Regular Expressions)

---

## ✨ PAN Validation Rules

A PAN is considered **valid** only if it satisfies all of the following conditions:

1.  **Length**: Must be exactly 10 characters long.
2.  **Format**: Must follow the structure `[A-Z]{5}[0-9]{4}[A-Z]{1}`.
    - First 5 characters must be uppercase letters.
    - Next 4 characters must be digits.
    - The last character must be an uppercase letter.
3.  **No Adjacent Repetition**: No two adjacent characters in the entire string can be the same (e.g., `AA...` or `...11...` are invalid).
4.  **No Sequential Characters**:
    - The first five alphabetic characters cannot be a sequence (e.g., `ABCDE...` is invalid).
    - The four numeric characters cannot be a sequence (e.g., `...1234...` is invalid).

---

## 🚀 How to Run

### Prerequisites
- Python 3.x
- Pip (Python package installer)

### 1. Clone the Repository
```bash
git clone https://github.com/Sethu0073/PAN_Validation_Project.git
cd PAN_Validation_Project
```

### 2. Create a Virtual Environment (Recommended)
```bash
# For Windows
python -m venv venv
venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
Install the required libraries from the `requirements.txt` file.
```bash
pip install -r requirements.txt
```

### 4. Run the Script
Execute the Python script to start the validation process.
```bash
python PAN_Validation.py
```

---

## 📊 Output

The script will generate an Excel file named `PAN VALIDATION RESULT.xlsx` in the `output` directory. This file contains two sheets:
1.  **`PAN Validations`**: A sheet with the original PAN numbers and their corresponding validation `Status` (Valid/Invalid).
2.  **`SUMMARY`**: A sheet summarizing the results, including:
    - Total Processed Records
    - Total Valid Count
    - Total Invalid Count
    - Total Missing/Dropped Records
