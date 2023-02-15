# PicoGPT-2

You've seen [openai/gpt-2](https://github.com/openai/gpt-2).

You've seen [karpathy/minGPT](https://github.com/karpathy/mingpt).

You've even seen [karpathy/nanoGPT](https://github.com/karpathy/nanogpt)!

But have you seen [picoGPT](https://github.com/kunalkashyap855/gpt2)??!?

`picoGPT` is an unnecessarily tiny and minimal implementation of [GPT-2](https://d4mucfpksywv.cloudfront.net/better-language-models/language_models_are_unsupervised_multitask_learners.pdf) in plain [NumPy](https://numpy.org). You can read the [original blog post](https://jaykmody.com/blog/gpt-from-scratch/?utm_source=tldrnewsletter#what-is-a-gpt%3F) for this implementation by [Jay Mody](https://github.com/jaymody).

picoGPT features:
* Fast? ❌ Nah, picoGPT is megaSLOW 🐌
* Training code? ❌ Error, 4️⃣0️⃣4️⃣ not found
* Batch inference? ❌ picoGPT is civilized, single file line, one at a time only
* top-p sampling? ❌ top-k? ❌ temperature? ❌ categorical sampling?! ❌ greedy? ✅
* Readable? `gpt2.py` ✅ `gpt2_pico.py` ❌
* Smol??? ✅✅✅✅✅✅ YESS!!! TEENIE TINY in fact 🤏

A quick breakdown of each of the files:

* `encoder.py` contains the code for OpenAI's BPE Tokenizer, taken straight from their [gpt-2 repo](https://github.com/openai/gpt-2/blob/master/src/encoder.py).
* `utils.py` contains the code to download and load the GPT-2 model weights, tokenizer, and hyper-parameters.
* `gpt2.py` contains the actual GPT model and generation code which we can run as a python script.
* `gpt2_pico.py` is the same as `gpt2.py`, but in even fewer lines of code. Why? Because why not 😎👍.

#### Dependencies
```bash
pip install -r requirements.txt
```

If you're using an M1 Macbook, you'll need to replace `tensorflow` with `tensorflow-macos`.

Tested on `Python 3.9.10`.

#### Usage
```bash
python gpt2.py "Alan Turing theorized that computers would one day become"
```

Which generates

```
 the most powerful machines on the planet.

The computer is a machine that can perform complex calculations, and it can perform these calculations in a way that is very similar to the human brain.
```

You can also control the number of tokens to generate, the model size (one of `["124M", "355M", "774M", "1558M"]`), and the directory to save the models:

```bash
python gpt2.py \
    "Alan Turing theorized that computers would one day become" \
    --n_tokens_to_generate 40 \
    --model_size "124M" \
    --models_dir "models"
```
