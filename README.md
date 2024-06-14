# GPTFromScratch
- Model deployed on https://huggingface.co/spaces/Chintan-Shah/ScratchGPTChar

## Trained an own GPT from scratch
- Used a normal GPT architecture with decoder only for prediction next token
- Trained for story dataset having small stories
- Tokenized on characters and not works or part words - This helped in ensuring able to train the model with limited vocab on small GPU
- Also tried training with OneCycleLR Scheduler but did not see any significant difference due to the size of the model as well as vocab probably
- Able to get decent results though not as good as other LLMs but then this is char based vocabulary
- Able to reduce the eval loss to almost 1.1370 and train loss to 1.1208
- Also trained for Shakespeare data from https://github.com/karpathy/nanoGPT/tree/master/data/shakespeare but deployed the Story one on huggingface

## Configurations used
- Optimizer: AdamW
- Scheduler: OneCycleLR (learning_rate = 1e-2)
- Loss: CrossEntropyLoss
- Dataset: roneneldan/TinyStories (Some part)
- AMP with Grad Scaler used

## Observations
- Stored stoi and itos also in files for hugging face spaces
- Usage of OneCycleLR and AMP does not help much in time or loss reduction
- Smaller dataset it seems it is better able to give the outcomes
- More iterations is improving the performance (Did max of 10000 iterations)

## Things want to do
- Train on Panchtantra stories and test
