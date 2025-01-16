This project is designed to extract structured data from various bid-related documents such as PDFs and HTML files. The data extracted includes fields such as bid number, due date, bid submission type, and more. The extracted information is saved as JSON files, which can be further processed for various applications.

Features
Extracts information from PDF and HTML files
Supports the extraction of multiple fields such as Bid Number, Due Date, Company Name, etc.
Utilizes NLP (Spacy) for better data extraction, especially for dates and company names
Saves extracted data as structured JSON files
Prerequisites
Before running the script, you need to have Python installed. You also need the following Python libraries:

PyPDF2 for parsing PDF files
beautifulsoup4 for parsing HTML files
spacy for natural language processing
re for regular expression matching
os and json for file handling
Requirements File
To install the necessary libraries, you can use the requirements.txt file:

txt
Copy
Edit
PyPDF2==2.10.5
beautifulsoup4==4.12.0
spacy==3.6.1
You can install these dependencies by running the following command:

bash
Copy
Edit
pip install -r requirements.txt
Setup Instructions
Clone or download this repository to your local machine.
Install the required dependencies listed in the requirements.txt file.
Make sure that the input_folder path is correctly set to the directory where your HTML and PDF files are stored.
The script will output the extracted data in a folder named output_files by default.
How It Works
The script processes files in the input_folder.
It reads the content of each file (either HTML or PDF).
Using regular expressions and NLP, it extracts structured data such as Bid Number, Due Date, Payment Terms, and more.
The extracted data is saved as a JSON file for each document.
Example of Extracted Data
json
Copy
Edit
{
    "bid_number": "12345",
    "title": "Laptop Bid",
    "due_date": "2025-01-30",
    "bid_submission_type": "Online",
    "pre_bid_meeting": "2025-01-15",
    "bid_bond_requirement": "Yes",
    "delivery_date": "2025-02-10",
    "payment_terms": "Net 30",
    "additional_documentation_required": "Yes",
    "manufacturer_for_registration": "Dell",
    "contract_or_cooperative_to_use": "State Contract",
    "model_number": "XPS 15",
    "part_number": "DELL123",
    "product": "Laptop",
    "contact_info": "contact@company.com",
    "company_name": "Tech Solutions",
    "bid_summary": "Bid for laptop purchase",
    "product_specification": "15-inch screen, 16GB RAM"
}
Running the Script
To run the script, execute the following command:

bash
Copy
Edit
python extract_bid_data.py
The script will process the files in the input_folder and save the output JSON files in the output_files directory.

Note
This assignment was completed as part of a learning exercise, and while I have strived to ensure accuracy and correctness, there might be areas where improvements can be made. I am a fast learner and continuously work on improving my skills by learning from previous experiences and mistakes. I am eager to further refine and optimize the solution based on feedback and new knowledge. Looking forward to making great contributions and creating impactful solutions at your company.

Conclusion
This project demonstrates my ability to process different document types (HTML, PDF) and extract structured information using regular expressions and NLP techniques. I am continuously learning and looking forward to applying these skills in real-world projects.
