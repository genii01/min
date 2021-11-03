# Hugginface Transformer Application

simple sample of transformer BERT & ALBERT


## requirements.txt

- torch==1.9.1
- transformers==4.12.2
- torchtext==0.11.0

## Usage

### inputdata example

```
positive	나름 괜찬항요 막 엄청 좋은건 아님 그냥 그럭저럭임... 아직 까지 인생 디퓨져는 못찾은느낌
negative	재질은플라스틱부분이많고요...금방깨질거같아요..당장 물은나오게해야하기에..그냥설치했어요..지금도 조금은후회중.....
```
### output 

```
positive, negative, negative, positive, ....
```
### Training

```bash
$ python hugging_plm_train.py --model_fn ./models/plm_tuned_model.pth --train_fn ./data/train.tsv --batch_size_per_device 8 --n_epochs 10
```

### Inference

```bash
$ cat ./data/review.sorted.uniq.refined.shuf.test.tsv | awk -F'\t' '{ print $2}' | head -n 30 | python3 classify_plm.py --model_fn ./models/plm_tuned_model.pth
```
