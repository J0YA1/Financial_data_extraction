# Financial Data Extraction from PDFs using NLP

## Overview
This project extracts financial data from PDF documents using Natural Language Processing (NLP). It utilizes:
- **PyMuPDF (fitz)** to extract text from PDFs.
- **Hugging Face Transformers** to analyze and extract key financial details using a Question-Answering (QA) model.
- **JSON storage** to save the extracted information for further processing.

## Features
- Reads financial reports in PDF format.
- Uses a pre-trained NLP model (`deepset/roberta-base-squad2`) to extract:
  - Company Name
  - Report Date
  - Profit Before Tax
  - Additional Financial Details
- Saves extracted data in a structured JSON format.
- Includes error handling for robustness.

## Prerequisites
Make sure you have the following dependencies installed:

```bash
pip install pymupdf transformers torch
```

## How It Works
1. **Extract Text from PDF**: Uses `fitz` (PyMuPDF) to read and extract text from PDF files.
2. **Load NLP Model**: Loads the `deepset/roberta-base-squad2` model for answering financial-related questions.
3. **Extract Key Information**: Uses the model to identify relevant financial data from the extracted text.
4. **Save to JSON**: The results are stored in a JSON file for further use.

## Usage
Run the script with a specified PDF file:

```bash
python main.py
```

Modify `pdf_path` and `output_path` in the script as needed.

## Output
The extracted financial data will be saved in `financial_data.json` in the following format:

```json
{
    "What is the company name?": "XYZ Ltd.",
    "What is the report date?": "December 31, 2024",
    "What is the profit before tax?": "$5.2 million"
}
```

## Error Handling
- If the PDF cannot be read, the script will exit with an error message.
- If the NLP model fails to extract data, a default response (`"Error extracting data"`) will be provided.

## Future Improvements
- Enhance accuracy with fine-tuned models for financial documents.
- Add OCR support for scanned PDFs.
- Improve UI/CLI for user-friendly interaction.

## License
This project is licensed under the MIT License.

