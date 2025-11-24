# PDF Text Extraction and Chunking

A Python script that efficiently extracts text from multiple PDF files (Batch Processing) and splits them into manageable chunks using parallel CPU processing.

## Features

- **Parallel Processing**: Utilizes all CPU cores for fast processing of multiple PDFs
- **Smart Text Chunking**: Uses LangChain's RecursiveCharacterTextSplitter for intelligent text segmentation
- **Metadata Tracking**: Each chunk retains information about its source PDF file
- **Error Handling**: Gracefully handles processing errors and continues with remaining files
- **Dataset Debugging**: Creates a .txt file that can be used for data cleaning and debugging faulty LLM responses

## Create your Project Directory & Navigate to the New Directory

```bash
mkdir PDFtoText

cd PDFtoText
```

## Create a Virtual Environment & Activate

```bash
Python3 -m venv PDFtoText_env

source PDFtoText_env/bin/activate
```

## Requirements

```bash
pip install -r req.txt
```

## Usage

1. Place your PDF files in the `./my_pdfs` directory (created automatically if it doesn't exist)
2. Run the script:

```bash
python process.py
```

3. Output is saved to `chunks_output.txt` with chunk separators

## Configuration

Adjust chunking parameters in the main block:

```python
chunk_size = 1000        # Characters per chunk
chunk_overlap = 200      # Overlap between consecutive chunks
```

## Output Format

Each chunk in the output file includes:
- Source filename
- Text content
- Separated by `---CHUNK SEPARATOR---`

## Example:

<img width="904" height="1016" alt="Screenshot from 2025-11-23 21-55-56" src="https://github.com/user-attachments/assets/78819c37-9139-4284-b07d-342ea4c271c0" />

## Performance

The script automatically uses all available CPU cores (`multiprocessing.cpu_count()`) for optimal performance when processing large numbers of PDFs.
