# YARA Malware Scanner GUI

A simple and user-friendly desktop application for scanning executable files (`.exe`) for potential malware using YARA rules. This tool is built with Python and Tkinter to provide a graphical interface for easy malware analysis.

## Description

This YARA Malware Scanner GUI is designed to help users quickly analyze executable files and identify potentially suspicious or malicious behaviors. It utilizes the powerful YARA pattern matching engine and comes pre-loaded with the `Advanced_Malware_Analysis.yara` rule set, which detects a range of common malware techniques and indicators.

**Key Features:**

*   **Graphical User Interface (GUI):** Easy to use with a simple and intuitive Tkinter interface.
*   **File Upload:** Allows users to easily select and upload `.exe` files for scanning via a file dialog.
*   **YARA Rule Scanning:** Scans uploaded files against the `Advanced_Malware_Analysis.yara` rule set.
*   **Color-Coded Results:** Displays scan results in a text area with color formatting to highlight suspicious findings.
*   **Detailed Indicator Output:**  Shows matched YARA rules and a list of indicators that triggered the rule, along with descriptions for each indicator to explain why they are considered suspicious.
*   **Error Handling:** Includes basic error handling for YARA library issues and file not found errors, displaying informative error messages in message boxes.

## Getting Started

**Prerequisites:**

*   **Python:** You need Python installed on your system (preferably Python 3.x).
*   **yara-python Library:** Install the `yara-python` library. You can install it using pip:
    ```bash
    pip install yara-python
    ```

**Running the Scanner:**

1.  **Download the files:** Download the `yara_scanner_gui.py` Python script and the `advanced_malware_analysis.yara` YARA rule file from this repository.
2.  **Place files in the same directory:** Ensure that both `yara_scanner_gui.py` and `advanced_malware_analysis.yara` are in the same directory.
3.  **Run the script:** Execute the Python script from your terminal or command prompt:
    ```bash
    python yara_scanner_gui.py
    ```
    This will launch the YARA Malware Scanner GUI application.

## Usage

1.  **Upload File:** Click the "Upload File" button.
2.  **Select Executable:** In the file dialog that opens, select the `.exe` file you want to scan and click "Open". The selected file name will be displayed below the button.
3.  **Scan File:** Click the "Scan File" button to start the YARA scan.
4.  **View Results:** The scan results will be displayed in the white text area below the "Scan File" button.
    *   **"Analysis Result: This file is suspicious!"** (Red): Indicates that the file triggered the YARA rules and is considered suspicious. The matched rule and indicators will be listed below with descriptions.
    *   **"Analysis Result: This file is not suspicious."** (Green): Indicates that no suspicious behavior was detected based on the current YARA rules.

## YARA Rule: `advanced_malware_analysis.yara`

The scanner uses the `Advanced_Malware_Analysis.yara` rule file. This rule is designed to detect a variety of suspicious behaviors often associated with malware, including:

*   Registry manipulation APIs
*   Network-related APIs
*   File system manipulation APIs
*   Process/execution manipulation APIs
*   Common malware strings (keywords)
*   Code obfuscation and packing indicators
*   Encryption related strings
*   Anti-debugging techniques
*   Polymorphism and metamorphism indicators
*   Code injection and hooking techniques

You can review and modify the `advanced_malware_analysis.yara` file to customize the detection capabilities.

## Error Handling

The application includes basic error handling to manage common issues:

*   **YARA Rule File Not Found:** If the `advanced_malware_analysis.yara` file is missing, an error message box will be displayed.
*   **YARA Errors:** If there are errors during YARA rule compilation or scanning, a YARA error message box will be displayed.
*   **File Selection Warning:** If you try to scan without selecting a file first, a warning message will prompt you to select a file.
*   **AttributeError Handling:** The code is designed to gracefully handle potential `AttributeError` exceptions if the `yara-python` library version does not provide expected attributes like `offset` and `matched_data` in the `StringMatch` object.

## Disclaimer

This tool is for basic malware analysis and educational purposes only. It is not a replacement for comprehensive anti-virus or security solutions.  The effectiveness of the scanner depends on the quality and coverage of the YARA rules used. Always use caution when analyzing potentially malicious files and consider using more advanced security tools and techniques for in-depth analysis and protection.

## Author

Youssef Reda

Username: Vigilante0101

## Date

Date Created/Updated: 2025-03-15

---

Feel free to contribute to this project or suggest improvements!
