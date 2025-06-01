# Character-Level Text Generator using RNN & LSTM

This project implements a character-level text generation model using PyTorch. We train both **RNN** and **LSTM** models on Jules Verne's *The Mysterious Island*, sourced from Project Gutenberg.

## Dataset

The dataset used is the full text of **The Mysterious Island** from [Project Gutenberg](https://www.gutenberg.org/ebooks/1268).

- The text is trimmed between:
  - `Start`: **"THE MYSTERIOUS ISLAND"**
  - `End`: **"End of the Project Gutenberg"**
- Total characters: `1,112,350`
- Unique characters: `80`

---

## Preprocessing

- Create a character-level vocabulary and mapping (`char2int` and `char_array`)
- Encode the entire text into integers
- Slice into fixed-length chunks of 41 (40 inputs + 1 target)

```python
'THE MYSTERIOUS ISLAND ***\\n\\n\\n\\n\\nProduced b'
```


# Model Architectures
Two models are implemented using PyTorch:

# LSTMModel
text
Copy
Edit

```python
Embedding → LSTM → Fully Connected (FC)
```

# RNNModel
text
Copy
Edit

```python
Embedding → RNN → Fully Connected (FC)
```

# Training
Training loop includes:

CrossEntropyLoss

Adam optimizer

Character-level accuracy per epoch

Start Training
python
Copy
Edit

```python
train_model(lstm_model, model_type='lstm')
train_model(rnn_model, model_type='rnn')
```

# Model Saving
After training, models are saved as:

lstm_model.pth

rnn_model.pth

To reload:

python
Copy
Edit

```python
lstm_model.load_state_dict(torch.load('lstm_model.pth'))
```

# Device Support
Automatically detects CUDA-enabled GPUs:

python
Copy
Edit

```python
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
```

Example Output
text
Copy
Edit

```python
Input (x):  'THE MYSTERIOUS ISLAND ***\\n\\n\\n\\n\\nProduced b'
Target (y): 'HE MYSTERIOUS ISLAND ***\\n\\n\\n\\n\\nProduced by'
```

# Future Work
Add text sampling/generation logic from trained models

Implement beam search or temperature sampling

Train on other literary texts for comparative results

📦 Requirements
Install required libraries:

bash
Copy
Edit

```python
pip install torch numpy
```
