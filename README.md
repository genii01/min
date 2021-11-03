# Hugginface Transformer Application

simple sample of transformer BERT & ALBERT


## requirements.txt

- torch==1.9.1
- transformers==4.12.2
- torchtext==0.11.0

## Usage

### Training

```bash
$ python hugging_plm_train.py --model_fn ./models/plm_tuned_model.pth --train_fn ./data/train.tsv --batch_size_per_device 8 --n_epochs 10
```

### Inference

```bash
$ cat ./data/review.sorted.uniq.refined.shuf.test.tsv | awk -F'\t' '{ print $2}' | head -n 30 | python3 classify_plm.py --model_fn ./models/plm_tuned_model.pth
```
