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

```bash
from transformers import AutoTokenizer, AutoModelForCausalLM


from transformers import AutoModelForCausalLM, AutoTokenizer

model_name = "tiiuae/lemoLLM1-10B-Instruct"

model = AutoModelForCausalLM.from_pretrained(
    model_name,
    torch_dtype="auto",
    device_map="auto"
)
tokenizer = AutoTokenizer.from_pretrained(model_name)

prompt = "How many hours in one day?"
messages = [
    {"role": "system", "content": "You are a helpful friendly assistant Falcon3 from TII, try to follow instructions as much as possible."},
    {"role": "user", "content": prompt}
]
text = tokenizer.apply_chat_template(
    messages,
    tokenize=False,
    add_generation_prompt=True
)
model_inputs = tokenizer([text], return_tensors="pt").to(model.device)

generated_ids = model.generate(
    **model_inputs,
    max_new_tokens=1024
)
generated_ids = [
    output_ids[len(input_ids):] for input_ids, output_ids in zip(model_inputs.input_ids, generated_ids)
]

response = tokenizer.batch_decode(generated_ids, skip_special_tokens=True)[0]
print(response)
```
