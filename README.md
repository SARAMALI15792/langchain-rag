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

Let me know if you need help implementing or testing this!
