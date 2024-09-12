# PDF_TO_Word
How to extract text from pdf and save to world?

# Here is a line-by-line breakdown of the provided Python script:
1. **import PyPDF2**: Import the `PyPDF2` library to handle PDF reading.
2. **from docx import Document**: Import the `Document` class from the `python-docx` library to handle Word document creation.
3. **pdf_file = 'Robinson-Crusoe-in-Levels-PDF.pdf'**: Define the path to the input PDF file.
4. **word_file = 'output1.docx'**: Define the path and name for the output Word file.
5. **def extract_text_from_pdf(pdf_file):**: Define a function to extract text from the provided PDF file.
6. **with open(pdf_file, 'rb') as file:**: Open the PDF file in binary read mode.
7. **pdf_reader = PyPDF2.PdfReader(file)**: Initialize the PDF reader object.
8. **text = ""**: Initialize an empty string to store extracted text.
9. **for page_num in range(len(pdf_reader.pages))**: Loop through each page in the PDF.
10. **page = pdf_reader.pages[page_num]**: Access the current page.
11. **text = page.extract_text() + "\n"**: Extract text from the page and add a newline.
12. **return text**: Return the extracted text from the PDF.
13. **def save_text_to_word(text, word_file):**: Define a function to save the extracted text to a Word file.
14. **doc = Document()**: Create a new Word document.
15. **doc.add_paragraph(text)**: Add the extracted text as a paragraph in the Word document.
16. **doc.save(word_file)**: Save the Word document to the specified file path.
17. **extracted_text = extract_text_from_pdf(pdf_file)**: Call the function to extract text from the PDF.
18. **save_text_to_word(extracted_text, word_file)**: Call the function to save the text to a Word file.
19. **print(f"Text Extracted from {pdf_file} and Saved to {word_file}")**: Print a message indicating the text has been extracted and saved.
