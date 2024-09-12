# PDF_TO_Word
How to extract text from pdf and save to world?

# Here is the provided Python script:
import PyPDF2
from docx import Document

pdf_file = 'Robinson-Crusoe-in-Levels-PDF.pdf'
word_file = 'output1.docx'

def extract_text_from_pdf(pdf_file):
    #open the PDF file
    with open(pdf_file, 'rb') as file:
        #initialize the PDF readern object
        pdf_reader = PyPDF2.PdfReader(file)
        text = ""
        
        #Extract the text from Pdf
        for page_num in range(len(pdf_reader.pages)):
            page = pdf_reader.pages[page_num]
            text = page.extract_text() + "\n"
    return text

def save_text_to_word(text, word_file):
    #create a new document
    doc = Document()
    
    #add the extracted text from PDF to Word file
    doc.add_paragraph(text)
    
    doc.save(word_file)
    
extracted_text = extract_text_from_pdf(pdf_file)

save_text_to_word(extracted_text, word_file)

print(f"Text Extracted from {pdf_file} and Saved to {word_file}")
