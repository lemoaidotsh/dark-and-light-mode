## The Lemo Foundation Models is a set of pretrained and instruct LLMs ranging from 1B to 10B parameters.

This repository contains the Lemo-10B-Instruct. It achieves state-of-the-art results (at the time of release) on reasoning, language understanding, instruction following, code, and mathematics tasks.

Lemo-10B-Instruct supports 4 languages (English, French, Spanish, Portuguese) and a context length of up to 32K.


##Model Details
## - Architecture
- Transformer-based causal decoder-only architecture
- 40 decoder blocks
- Grouped Query Attention (GQA) for faster inference: 12 query heads and 4 key-value heads
- Wider head dimension: 256
- High RoPE value to support long context understanding: 1000042
- Uses SwiGLu and RMSNorm
- 32K context length
- 131K vocab size
