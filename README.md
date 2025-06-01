# write_readme.py

readme_text = """
# 🧠 Character-Level Text Generator using RNN & LSTM

This project implements a character-level text generation model using PyTorch. We train both **RNN** and **LSTM** models on Jules Verne's *The Mysterious Island*, sourced from Project Gutenberg.

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/The_Mysterious_Island_by_Jules_Verne_1874_First_edition.jpg/800px-The_Mysterious_Island_by_Jules_Verne_1874_First_edition.jpg" alt="The Mysterious Island Cover" width="300"/>
</p>

---

## 📚 Dataset

The dataset used is the full text of **The Mysterious Island** from [Project Gutenberg](https://www.gutenberg.org/ebooks/1268).

- The text is trimmed between:
  - `Start`: **"THE MYSTERIOUS ISLAND"**
  - `End`: **"End of the Project Gutenberg"**
- Total characters: `1,112,350`
- Unique characters: `80`

---

## ⚙️ Preprocessing

- Create a character-level vocabulary and mapping (`char2int` and `char_array`)
- Encode the entire text into integers
- Slice into fixed-length chunks of 41 (40 inputs + 1 target)

```python
'THE MYSTERIOUS ISLAND ***\\n\\n\\n\\n\\nProduced b'
