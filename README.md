# RFP Document Extraction Tool

## Setup Instructions

### Input Folder Setup
The script expects the RFP documents in PDF or HTML format to be placed in the `INPUT_FOLDER`. You can set the path to the folder containing these files.

### Output Folder Setup
The script will output the extracted structured data as JSON files into the `OUTPUT_FOLDER`.

## Directory Structure
Ensure the directory structure is as follows:
```
.
├── rfp_extraction.py    # The main Python script for RFP document extraction
├── input_files/        # Directory containing input PDF/HTML files
├── output_files/       # Directory for saving extracted JSON files
```

## How to Use

1. **Prepare Input Files**
   - Place the RFP documents (PDF or HTML) in the `input_files` directory.

2. **Run the Script**
   - Execute the script `rfp_extraction.py`:
   ```bash
   python rfp_extraction.py
   ```
   - The script will automatically process the files in the `input_files` directory and save the results as JSON files in the `output_files` directory.

3. **View Results**
   - The structured data for each RFP document will be saved as a JSON file with the same name as the input file but with a `.json` extension.

## Output Example
An example of the output JSON structure:

```json
{
    "Addendum 1 RFP JA-207652 Student and Staff Computing Devices.pdf": {
        "bid_number": "JA-207652",
        "title": "RFP JA-207652 Student and Staff Computing Devices",
        "due_date": "2024-12-01",
        "bid_submission_type": "Online",
        "pre_bid_meeting": "pre-bid call, a Dallas ISD representative mentioned OEM warranty only...",
        "installation_required": true,
        "bid_bond_requirement": "$1,000",
        "delivery_date": "2024-12-15",
        "payment_terms": "Net 30",
        "additional_documentation_required": "Yes",
        "manufacturer_for_registration": "XYZ Corp",
        "contract_or_cooperative_to_use": "XYZ Cooperative",
        "model_number": "ABC123",
        "part_number": "XYZ456",
        "product": "Laptop",
        "contact_info": "contact@xyzcorp.com",
        "company_name": "XYZ Corporation",
        "bid_summary": "A bid to provide laptops to Dallas ISD",
        "product_specification": "Laptop must meet minimum requirements for educational use."
    }
}
```

## Notes
The script uses regex patterns to extract key fields, including bid number, title, due date, and others. If regex fails to find certain fields, spaCy NLP is used as a fallback to extract additional information such as dates and organization names.

If you need to add or modify fields, you can update the `PATTERNS` dictionary to include new or adjusted regular expressions.

## Troubleshooting

### Common Issues

1. **Missing NLP Model**
   - If you encounter an error related to the spaCy model, make sure to download the required model using the following command:
   ```bash
   python -m spacy download en_core_web_sm
   ```

2. **Unsupported File Format**
   - If the input document is neither a PDF nor an HTML file, the script will skip it with a warning.
   - Ensure that your input files are in supported formats.

3. **Incorrect Output**
   - If some fields are missing from the output, you may need to fine-tune the regex patterns or adjust the NLP extraction rules in the script.
