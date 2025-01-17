# RFP Document Extraction Tool

## Disclaimer
This assignment was completed as part of a learning exercise, and while I have strived to ensure accuracy and correctness, there might be areas where improvements can be made. I am a fast learner and continuously work on improving my skills by learning from previous experiences and mistakes. I am eager to further refine and optimize the solution based on feedback and new knowledge. Looking forward to making great contributions and creating impactful solutions at your company.

## Key Learning Outcomes
- Implemented regex pattern matching for document parsing
- Utilized spaCy NLP for advanced text extraction
- Developed structured JSON output format
- Applied error handling and fallback mechanisms

## Technologies Used
- Python
- spaCy NLP
- Regular Expressions
- JSON

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
    "bid_number": null,
    "title": "Address:  City, State and Zip Code:",
    "due_date": "July 9, 2024",
    "bid_submission_type": "Online",
    "pre_bid_meeting": null,
    "installation_required": true,
    "bid_bond_requirement": null,
    "delivery_date": null,
    "payment_terms": null,
    "additional_documentation_required": null,
    "manufacturer_for_registration": null,
    "contract_or_cooperative_to_use": null,
    "model_number": null,
    "part_number": null,
    "product": null,
    "contact_info": null,
    "company_name": "Submitter's Name/Title:",
    "bid_summary": null,
    "product_specification": null
}
```

## Notes
The script uses regex patterns to extract key fields, including bid number, title, due date, and others. If regex fails to find certain fields, spaCy NLP is used as a fallback to extract additional information such as dates and organization names.

If you need to add or modify fields, you can update the `PATTERNS` dictionary to include new or adjusted regular expressions.

## Testing
The script has been tested with various RFP documents to ensure reliable extraction. Unit tests are planned for future iterations.

## Future Improvements
- Enhance regex patterns for better accuracy
- Add support for more document formats (e.g., DOC, DOCX)
- Implement batch processing capabilities
- Create a web interface for easier file uploads
- Add comprehensive unit testing
- Implement logging for better debugging
- Add validation for extracted data

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
