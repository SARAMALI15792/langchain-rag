# langchain-rag  --> documents loader
Here’s a cleaned-up and structured step-by-step version of the summary you provided:

### Steps:

1. **Install `chain`**  
   Use the following command to install `chain` via pip:  
   ```bash
   pip install chain
   ```

2. **Install `chain_Community`**  
   Use pip to install `chain_Community`:  
   ```bash
   pip install chain_Community
   ```

3. **Load a PDF file using `pyPDFLoader`**  
   Install and use `pyPDFLoader` to load a PDF file. Example:  
   ```python
   from pyPDFLoader import Loader
   loader = Loader("content/The-7-Habits-of-Highly-Effective-People.pdf")
   ```

4. **Display the first three pages of the PDF**  
   Load and display the first three pages:  
   ```python
   pages = loader.load()
   print(pages[0:3])
   ```

5. **Load a web page using `WebBaseLoader`**  
   Use `WebBaseLoader` to load a webpage. Example:  
   ```python
   from WebBaseLoader import Loader
   loader = Loader("https://example.com")
   ```

6. **Display the content of the loaded web page**  
   Load the content of the webpage and display it:  
   ```python
   content = loader.load()
   print(content[0])
   ``` 
#Langchain ---> Text Spliters-
Here’s a clear step-by-step version of the summary for text splitting:

---

### Steps for Text Splitting:

1. **Install Necessary Libraries**  
   - Install `LangChain` using pip:  
     ```bash
     pip install langchain
     ```
   - Install `LangChain Text Splitters` using pip:  
     ```bash
     pip install langchain-text-splitters
     ```

2. **Load a Text Document**  
   - Read the content of a text file (e.g., `sample.txt`) into a variable `docu`:  
     ```python
     with open("sample.txt", "r") as file:
         docu = file.read()
     ```

3. **Use `CharacterTextSplitter`**  
   - Create an instance of `CharacterTextSplitter` with the following parameters:  
     - Separator: `\n` (newline)  
     - Chunk size: `500`  
     - Overlap: `200`  
   - Split the document into chunks:  
     ```python
     from langchain.text_splitter import CharacterTextSplitter

     text_splitter = CharacterTextSplitter(separator="\n", chunk_size=500, chunk_overlap=200)
     chunks = text_splitter.create_documents([docu])
     ```

   - Note: This method splits text at the defined separator but may produce chunks larger than the specified size.

4. **Use `RecursiveCharacterTextSplitter`**  
   - Create an instance of `RecursiveCharacterTextSplitter` with the following parameters:  
     - Chunk size: `1004`  
     - Overlap: `260`  
   - Split the document into chunks:  
     ```python
     from langchain.text_splitter import RecursiveCharacterTextSplitter

     recursive_splitter = RecursiveCharacterTextSplitter(chunk_size=1004, chunk_overlap=260)
     recursive_chunks = recursive_splitter.create_documents([docu])
     ```

   - Note: This splitter tries to split text by paragraphs, then sentences, and finally words. It aims to keep semantically related pieces of text together.

---

These steps highlight two methods for splitting text into smaller chunks using LangChain's text splitter tools. Let me know if you’d like further clarification!
