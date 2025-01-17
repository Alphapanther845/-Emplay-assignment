##Bid Information Extraction from HTML and PDF Files
This project extracts structured information from HTML and PDF files (e.g., bid documents) using a combination of regular expressions and Natural Language Processing (NLP) techniques.

##Features:
HTML and PDF Parsing: The code can handle both HTML and PDF files.
Bid Data Extraction: Extracts key bid-related information such as bid number, title, due date, bid submission type, and more.
NLP for Fallback Extraction: Utilizes spaCy NLP to extract specific information like dates, organizations, and monetary values when the regular expressions fail.
Data Saving: The extracted data is saved as JSON files for easy use.
How NLP is Used:
The code leverages spaCy, a popular NLP library, to enhance the extraction process:

Named Entity Recognition (NER): SpaCy’s pre-trained NER model (en_core_web_sm) is used to identify and extract specific entities from the text, such as:
Dates: Helps identify due dates or delivery dates when regex fails.
Organizations (ORG): Identifies company names associated with the bid.
Money: Captures bid bond requirements and other monetary values.
Text Parsing: SpaCy processes the text extracted from HTML and PDF files. It analyzes the linguistic structure of the text, recognizing named entities that match specific categories (e.g., dates, organizations, money).
Prerequisites:
Ensure that the following libraries are installed:

bash
Copy
Edit
pip install PyPDF2 beautifulsoup4 spacy
python -m spacy download en_core_web_sm
PyPDF2: For extracting text from PDF files.
BeautifulSoup: For parsing HTML files.
spaCy: For natural language processing tasks, especially Named Entity Recognition.
File Structure:
Input Folder: Place your HTML and PDF files in the INPUT_FOLDER directory.
Output Folder: The structured data will be saved as JSON files in the OUTPUT_FOLDER directory.
Steps to Use:
Prepare Input Files:

Add your HTML and PDF bid documents to the INPUT_FOLDER (e.g., ./input_files).
Configure the Code:

Modify the INPUT_FOLDER and OUTPUT_FOLDER paths if necessary. The input folder should contain the bid files, and the output folder is where the JSON files with structured data will be saved.
Run the Code:

Run the script to parse the files and extract structured data.
bash
Copy
Edit
python extract_bid_data.py
Check Output:
After running the script, check the OUTPUT_FOLDER for the generated JSON files. Each file will contain the structured data extracted from the respective bid document.
Example JSON Output:
The extracted structured data will be saved in a format like this:

json
Copy
Edit
{
    "bid_number": "12345",
    "title": "Bid for Software Development",
    "due_date": "2024-03-01",
    "bid_submission_type": "Online",
    "pre_bid_meeting": "2024-02-15",
    "bid_bond_requirement": "$5000",
    "delivery_date": "2024-04-01",
    "payment_terms": "30 days",
    "additional_documentation_required": "Yes",
    "manufacturer_for_registration": "ABC Corp",
    "contract_or_cooperative_to_use": "ABC Coop",
    "model_number": "XYZ123",
    "part_number": "ABC456",
    "product": "Software Development",
    "contact_info": "John Doe, john.doe@example.com",
    "company_name": "TechSolutions Inc.",
    "bid_summary": "Bid for providing software development services.",
    "product_specification": "Software for enterprise applications."
}
Notes:
Unsupported Formats: The code only supports .html and .pdf files. If you need to process other file formats, modify the script accordingly.
Custom Regex Patterns: The regular expressions can be modified to adapt to different document structures.
Error Handling: Errors are logged for each file, so you can easily debug issues in the document processing.
Conclusion:
This script provides a quick way to extract structured bid information from HTML and PDF documents using both traditional regex and advanced NLP techniques, making it a powerful tool for automating data extraction in bid-related documents.

This README provides an overview of how NLP is applied in your code and guides users through the setup and execution of the project.








