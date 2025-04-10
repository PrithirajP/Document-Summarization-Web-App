
```markdown
# 📄 Document Summarization App using LaMini-Flan-T5

This is a Streamlit web application for **automatic document summarization** using the [LaMini-Flan-T5-248M](https://huggingface.co/MBZUAI/LaMini-Flan-T5-248M) large language model. It allows users to upload PDF files and receive concise, high-quality summaries powered by modern natural language processing tools from Hugging Face and LangChain.

---

## 🔗 Model Used

We use the [`MBZUAI/LaMini-Flan-T5-248M`](https://huggingface.co/MBZUAI/LaMini-Flan-T5-248M) model from Hugging Face. It is a fine-tuned version of T5 designed for instruction-following tasks like summarization, translation, and more. This lightweight model balances efficiency with accuracy, making it suitable for real-time web apps.

---

## 🧠 How the App Works

1. **User Uploads a PDF**  
   The app uses Streamlit’s file uploader to receive PDF input from the user.

2. **Document Processing**  
   The PDF is loaded and split into manageable text chunks using:
   - `PyPDFLoader` (from LangChain)
   - `RecursiveCharacterTextSplitter` for breaking the text into overlapping segments

3. **Summarization Pipeline**  
   The `LaMini-Flan-T5-248M` model and tokenizer are loaded using Hugging Face Transformers. A summarization pipeline is initialized with the model and configured with a desired summary length.

4. **Display**  
   The app shows:
   - The uploaded PDF (rendered with base64 encoding)
   - The generated summary side-by-side for quick reference

---

## 🚀 How to Run Locally

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/document-summarization-app.git
cd document-summarization-app
```

### 2. Install Dependencies
Create a virtual environment (optional but recommended), then install requirements:

```bash
pip install -r requirements.txt
```

### 3. Create a `data` Directory
```bash
mkdir data
```

This is where uploaded PDFs will be saved temporarily.

### 4. Run the App
```bash
streamlit run app.py
```

Then open your browser at [http://localhost:8501](http://localhost:8501) to use the app.

---

## 📦 Requirements

Here are the major Python libraries used:

- `streamlit`
- `transformers`
- `torch`
- `langchain`
- `pypdf`
- `scikit-learn` (optional for LangChain internals)

You can install them via:

```bash
pip install streamlit transformers torch langchain pypdf
```

> A full `requirements.txt` is provided in this repo.

---

## 📁 Project Structure

```
📦 document-summarization-app
├── app.py                  # Main Streamlit app
├── requirements.txt        # Python dependencies
└── data/                   # Folder to temporarily store uploaded PDFs
```

---

## 📌 Notes

- This app currently supports only **PDF documents**.
- Summaries are generated using all text extracted from the document. For large PDFs, processing time may vary.
- The model uses a `max_length` of 500 and `min_length` of 50 for summaries, which you can tweak in `app.py`.

---

## 🙌 Acknowledgements

- [MBZUAI](https://www.mbzuai.ac.ae/) for open-sourcing the LaMini model
- [Hugging Face](https://huggingface.co/) for Transformers and model hosting
- [LangChain](https://www.langchain.com/) for document loaders and text splitting utilities
- [Streamlit](https://streamlit.io/) for making ML app deployment easy

---

## 🗣️ License

This project is licensed under the MIT License. See `LICENSE` for details.

```

Would you like me to also generate the `requirements.txt` file now?
