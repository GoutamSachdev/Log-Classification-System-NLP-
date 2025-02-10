# Log-Classification-System-NLP LLM-(DEEPSEEK)


A hybrid log classification system combining **Regex**, **Sentence Transformers**, and **LLMs** to classify log messages effectively.

---

## **Features**
- **Regex**: Handles simple, predictable patterns.
- **Sentence Transformer + Logistic Regression**: Classifies complex patterns with sufficient training data.(SentenceTransformer)
- **LLM (Large Language Models)**: Handles complex patterns when training data is limited. (deepseek-r1-distill-llama-70b)


+-------------------+
|   Log Message     |
+-------------------+
          |
          v
+-------------------+
| Regex Classification |
+-------------------+
          |
   +------+------+
   |             |
   v             v
+--------+    +--------+
| Valid  |    | Unknown|
| Class  |    |        |
+--------+    +--------+
          |
          v
+-------------------+
| Enough training?  |
+-------------------+
          |
   +------+------+
   |             |
   v             v
+--------+    +--------+
|  Yes   |    |   No   |
+--------+    +--------+
          |             |
          v             v
+-------------------+  +-------------------+
| BERT Classification|  | LLM Classification |
+-------------------+  +-------------------+
```


## **Folder Structure**
```
Log-Classification-System-NLP/
├── training/                  # Training code for models
├── models/                    # Saved models
├── resources/                 # Test files, outputs, images
├── server.py                  # FastAPI server code
└── requirements.txt           # Dependencies
```

---

## **Setup**
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Run the FastAPI server:
   ```bash
   uvicorn server:app --reload
   ```
3. Access the API:
   - Main endpoint: `http://127.0.0.1:8000/`
   - Swagger docs: `http://127.0.0.1:8000/docs`
   - ReDoc docs: `http://127.0.0.1:8000/redoc`

---

## **Usage**
- Upload a CSV file with columns `source` and `log_message`.
- The output CSV will include a `target_label` column with classified labels.

---

## **License**

Contact: [gksachdev46@gmail.com](mailto:gksachdev46@gmail.com)
