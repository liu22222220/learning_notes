# Andrej Karpathy LLM Tutorials

Youtube watchlist: 
https://youtube.com/playlist?list=PLT0ilKMS5ZPyOvTy63ojqVEsVGXXVDKBZ&si=dyXNrm4LgbleP9kc

## Let's build the GPT Tokenizer ([link](https://www.youtube.com/watch?v=zduSFxRajkE&list=PLT0ilKMS5ZPyOvTy63ojqVEsVGXXVDKBZ&index=1&ab_channel=AndrejKarpathy))

### Links
- Google colab for the video: https://colab.research.google.com/drive/1y0KnCFZvGVf_odSfcNAws6kcDD7HsI0L?usp=sharing
- GitHub repo for the video: minBPE https://github.com/karpathy/minbpe/blob/master/exercise.md

###  Paper
- The programmer’s guide to Unicode
- MEGABYTE: Predicting million-byte sequences with multi scale transformers
- Language Models are Unsupervised Multitask Learners
    - Introduced GPT 2
- Learning to Compress Prompts with Gist Tokens
- Taming Transformers for High-resolution Image Synthesis

### Unicode
Emojis are represented with Unicode encodings: UTF-8, UTF-16, UTF-32

UTF-8 is only one of the different encodings that are compatible with older standards, such as ASCII and etc

### Byte-pair encoding
Recursively replace most frequent byte pairs with a new token, until the vocab dict reaches the desired size.

GPT-2 uses byte-pair encoding, but avoid concatenating words and punctuations
```
gpt2pat = re.compile(r"""'s|'t|'re|'ve|'m|'ll|'d| ?\p{L}+| ?\p{N}+| ?[^\s\p{L}\p{N}]+|\s+(?!\S)|\s+""")
```

### Tiktoken
- Tokenizer web demo:
https://tiktokenizer.vercel.app/
- Extend TikToken: 
https://github.com/openai/tiktoken?tab=readme-ov-file#extending-tiktoken


### Exntending LLM
Resize model parameters, and training with freezing base model:
- token_embedding_table
- lm_head

Consideration for adding tokens:
- If token size grows, the training data per token will go down, and most tokens will be under-trained

taming transformers for high-resolution image synthesis


## The spelled-out intro to neural networks and backpropagation: building micrograd ([link](https://www.youtube.com/watch?v=VMj-3S1tku0&list=PLT0ilKMS5ZPyOvTy63ojqVEsVGXXVDKBZ&index=2&ab_channel=AndrejKarpathy))

### Links:
- micrograd on github: https://github.com/karpathy/micrograd
- jupyter notebooks I built in this video: https://github.com/karpathy/nn-zero-to-hero/tree/master/lectures/micrograd


### Neuron
```
# tanh: hyperbolic tangent activation function
n = tanh(sum(w_i * x_i) + b)
```



## Python tricks
```
for pair in zip(ids, ids[1:]):
    ...
```

```
# convert to int
ids = map(int, tokens)
```

```
# working with unicode
ord(), chr()
```

```
# sorting
sort(data, key=data.get)
```

```
__mul__()
__rmul__()
```

## Other tricks

Lucide icons: https://github.com/lucide-icons/lucide/tree/main

Graphiz to visualize nodes: https://graphviz.org/