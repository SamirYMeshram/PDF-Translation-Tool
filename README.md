## **📘 PDF Translation Tool**

## **📖 Overview**

The **PDF Translation Tool** is a Python-based desktop application that allows users to translate the text content of PDF files into a target language while maintaining the original layout (text positions, font styles, and image preservation). The tool uses **Tkinter** for the graphical user interface, **PyMuPDF (fitz)** for PDF extraction and manipulation, and **Google Translate API** for the translation process. The final result is a translated PDF file that preserves the layout of the original document, including fonts and images.

This tool helps in easily translating any PDF documents such as e-books, reports, or manuals into different languages with high-quality preservation of the original format.

## **✨ Key Features**

- **Text Extraction**: Extracts text, font details (size, position), and images from PDFs.
- **Google Translate Integration**: Translates the extracted text into the target language.
- **Layout Preservation**: Maintains the original text formatting, font styles, and images in the translated PDF.
- **Multi-language Support**: Supports translating to various languages with simple language code input.
- **Image Handling**: Extracts and embeds images from the original PDF into the translated version.
- **GUI**: Provides an interactive Tkinter interface for an easy user experience.
- **Retry Mechanism**: Automatically retries failed translations for robust performance.
- **Text Chunking**: Splits large texts into manageable chunks to prevent timeouts during translation.
  
## **📸 Screenshots**

![Screenshot 1](screenshots/screenshot1.png)  
*Main interface of the PDF Translation Tool.*

![Screenshot 2](screenshots/screenshot2.png)  
*Translated PDF preview after processing.*

---

## **🛠️ Technologies Used**

- **Python**: The primary programming language for the project.
- **PyMuPDF (fitz)**: Used for extracting text and images from PDF files.
- **googletrans**: Python library for Google Translate integration.
- **Tkinter**: Used for building the graphical user interface.
- **Requests**: Handles API requests for translations.

---

## **📁 Folder Structure**

```
📦 PDF-Translation-Tool  
├── 📂 PDFoutput/           # Stores generated translated PDFs  
├── 📄 pdf_translation_tool.py  # Main application code  
├── 📄 requirements.txt     # Required libraries for the project  
└── 📄 README.md            # Project documentation (this file)  
```

---

## **⚙️ Installation and Setup**

### **1️⃣ Clone the Repository**

```bash
git clone https://github.com/SamirYMeshram/PDF-Translation-Tool.git
cd PDF-Translation-Tool
```

### **2️⃣ Create a Virtual Environment (Optional but Recommended)**

```bash
python -m venv venv
source venv/bin/activate  # For Linux/MacOS
venv\Scripts\activate     # For Windows
```

### **3️⃣ Install Required Libraries**

Install all the dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

### **4️⃣ Run the Application**

After installing the dependencies, you can run the application:

```bash
python pdf_translation_tool.py
```

This will open a full-screen Tkinter window where you can upload a PDF and begin translating it into your chosen language.

---

## **📚 How to Use the Application**

1. **Launch the Application**: Run the script `pdf_translation_tool.py` to open the tool.
2. **Upload a PDF File**: Click the **Upload PDF** button to select your PDF from your system.
3. **Select Target Language**: Enter the language code (e.g., "es" for Spanish) in the provided input box.
4. **Translate**: The program will automatically extract text, translate it, and create a translated PDF while keeping the layout intact.
5. **View Output**: Once the process is complete, you can access the translated PDF from the output folder.

---

## **📋 Algorithm**

### **1️⃣ Upload PDF**

- The user uploads a PDF file through the file dialog.
- The tool then extracts the text and images from the PDF using **PyMuPDF (fitz)**.

### **2️⃣ Text Extraction**

- Extract the raw text and fonts from the PDF using **PyMuPDF**.
- In case the PDF is an image-based document, the tool will use **OCR** (Optical Character Recognition) via **easyocr** to extract text from the images.

### **3️⃣ Text Translation**

- The extracted text is divided into smaller chunks to avoid overloading the translation API.
- Each chunk is then sent to the **Google Translate API** for translation into the desired language.

### **4️⃣ Layout Preservation**

- The translated text is reinserted into the PDF, maintaining the original layout (text positions, font styles, and sizes).
- **PyMuPDF** handles the PDF reconstruction, and images are re-added as they were in the original document.

### **5️⃣ Generate Translated PDF**

- The translated content is compiled into a new PDF and saved in the `PDFoutput` folder, keeping the layout, font, and image positioning intact.

---

## **💻 Code Explanation**

### **pdf_translation_tool.py**

This file contains all the main logic for:
- Extracting text and images from the PDF.
- Translating text using Google Translate.
- Recreating the translated PDF with layout preservation.
- Implementing the graphical user interface with Tkinter.

### **Key Functions**

| **Function**                      | **Description**                                                                 |
|----------------------------------- |------------------------------------------------------------------------------- |
| `extract_text_from_pdf()`          | Extracts the plain text and font details (position, size) from the PDF.         |
| `extract_images_from_pdf()`       | Extracts images and their metadata (position, size) from the PDF.               |
| `translate_text()`                 | Sends text to the Google Translate API for translation.                        |
| `recreate_pdf_with_translations()` | Reconstructs the PDF with translated text while preserving layout and images.  |
| `generate_output_pdf()`            | Saves the final translated PDF to the output folder.                           |
| `upload_pdf()`                     | Manages the PDF upload process and translation trigger.                         |
| `get_unique_filename()`            | Ensures unique output filenames for translated PDFs.                           |

---

## **📋 Requirements**

To run the application, you’ll need the following libraries:

```
tkinter
PyMuPDF
googletrans==4.0.0-rc1
requests
```

To install all the dependencies, run:

```bash
pip install -r requirements.txt
```

---

## **📋 Troubleshooting**

**Issue**: Translation error or timeout  
**Solution**: The tool has retry logic built-in, but if it fails repeatedly, check the Google Translate API for service disruptions.

**Issue**: Layout issue in the generated PDF  
**Solution**: Ensure that the PDF contains well-defined text and clear images. Some complex layouts may cause slight distortions in the output.

---

## **🔮 Possible Enhancements**

- **Text Formatting**: Improve font handling for more complex PDFs with varying text styles.
- **Batch Processing**: Add functionality to translate multiple PDFs in one batch.
- **Cloud Integration**: Provide the option to save translated PDFs to cloud storage services like Google Drive or Dropbox.
- **Error Handling Enhancements**: Improve retry logic and add user-friendly error notifications.

---

## **🤝 Contributing**

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch for your feature (`git checkout -b feature-name`).
3. Commit your changes (`git commit -m "Added feature"`).
4. Push to your branch (`git push origin feature-name`).
5. Open a pull request describing your changes.

---

## **📝 License**

This project is licensed under the **MIT License**. See the `LICENSE` file for more details.

---

## **👤 Author**

- **GitHub**: [SamirYMeshram](https://github.com/SamirYMeshram)
- **Email**: samirYmeshram@gmail.com

---

This README provides a detailed and professional overview of the PDF Translation Tool, explaining all key features, installation instructions, usage details, and how to contribute to the project.
