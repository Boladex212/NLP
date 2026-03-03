# NLP
How model NLP work: the transformer 
Raw text
    ↓  Tokenization
Tokens (subword units)
    ↓  Embedding
Vectors in high-dimensional space
    ↓  Transformer layers (attention + feed-forward)
Contextual representations
    ↓  Task-specific head
Output (classification / generation / translation / etc.)

text = "The transformer changed NLP forever."

 Tokenization
tokens = text.lower().split()

 Embedding (mock vectors)
import random
embeddings = {tok: [random.uniform(-1,1) for _ in range(8)] for tok in tokens}

 Transformer layer (mock attention)
defattention(vecs):
    return [[sum(x)/len(x) for x in zip(*vecs)]]  # simplified mean pooling

vectors = list(embeddings.values())
context = attention(vectors)

 Task-specific head (mock classification)
score = sum(context[0]) / len(context[0])
output = "positive" if score > 0 else "negative"

print(f"Tokens     : {tokens}")
print(f"Context vec: {[round(x,2) for x in context[0]]}")
print(f"Output     : {output}")
