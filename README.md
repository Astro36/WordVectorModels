# Word Vector Models

> Pre-trained Word Vector Models of 30+ Languages

This project has two purposes. First of all, I'd like to share some of my experience in nlp tasks such as segmentation or word vectors. The other, which is more important, is that probably some people are searching for pre-trained word vector models for non-English languages. Alas! English has gained much more attention than any other languages has done. Check [this](https://github.com/3Top/word2vec-api) to see how easily you can get a variety of pre-trained English word vectors without efforts. I think it's time to turn our eyes to a multi language version of this.

## Requirements

Required Python 3.

See [requirements](./src/requirements.txt)

### Language Supports

If using below language, you also need additional library.

* Chinese: `jieba`
* Japanese: `mecab`
* Korean: `konlpy`
* Thai: `pythai`
* Vietnamese: `pyvi`

### Word Embeddings

If training your own model, you have to install below library.

* fastText: [fasttext](https://github.com/facebookresearch/fastText)
* Word2Vec: `gensim`

## Background / References

* Check [this](https://en.wikipedia.org/wiki/Word_embedding) to know what word embedding is.
* Check [this](https://en.wikipedia.org/wiki/Word2vec) to quickly get a picture of Word2vec.
* Check [this](https://github.com/facebookresearch/fastText) to install fastText.
* Watch [this](https://www.youtube.com/watch?v=T8tQZChniMk&index=2&list=PL_6hBtWGKk2KdY3ANaEYbxL3N5YhRN9i0) to really understand what's happening under the hood of Word2vec.
* Go get various English word vectors [here](https://github.com/3Top/word2vec-api) if needed.

## Work Flow

* STEP 1-1. Download the [wikipedia database backup dumps](https://dumps.wikimedia.org/backup-index.html) of the language you want (For example, for english wiki go to [https://dumps.wikimedia.org/enwiki/](https://dumps.wikimedia.org/enwiki/), click the latest timestamp, and download the `enwiki-YYYYMMDD-pages-articles-multistream.xml.bz2` file).
* STEP 1-2. Install requirements packages.
* STEP 2. Extract running texts to `./data` directory.
* STEP 3. Run `./src/build_corpus.py`.

```bash
python build_corpus.py --lcode=ko
```

* STEP 4-1. Run `./src/train_word2vec.py` to get Word2Vec word vectors:

```bash
python train_word2vec.py --lcode=en --vector_size=300 --window_size=5 --vocab_size=50000 --num_negative=5
```

* STEP 4-2. Run `./script/fasttext.sh` to get fastText word vectors.

## Pre-trained models

Two types of pre-trained models are provided. `w` and `f` represent `word2vec` and `fastText` respectively.

Check language code [here](./Language.md).

| Language | ISO 639-1 | Vector Size | Corpus Size | Vocabulary Size |
| -------- | --------- | ----------- | ----------- | --------------- |
|[Bengali(w)](https://drive.google.com/open?id=0B0ZXk88koS2KX01rR2dyRWpHNTA) & [Bengali(f)](https://www.dropbox.com/s/xmi5xhqlu60bwfa/bn.tar.gz?dl=0)| bn | 300 | 147M | 10059 |
|[Catalan(w)](https://drive.google.com/open?id=0B0ZXk88koS2KYkd5OVExR3o1V1k) & [Catalan(f)](https://www.dropbox.com/s/pd59l1mwvg4hocp/ca.tar.gz?dl=0) | ca | 300 | 967M | 50013 |
|[Chinese(w)](https://drive.google.com/open?id=0B0ZXk88koS2KNER5UHNDY19pbzQ) & [Chinese(f)](https://www.dropbox.com/s/il7syxqmnusul8c/zh.tar.gz?dl=0) | zh | 300 | 1G | 50101 |
|[Danish(w)](https://drive.google.com/open?id=0B0ZXk88koS2KcW1aTGloZnpCMGM) & [Danish(f)](https://www.dropbox.com/s/x2ekc79m8p6ycue/da.tar.gz?dl=0) | da | 300 | 295M | 30134 |
|[Dutch(w)](https://drive.google.com/open?id=0B0ZXk88koS2KQnNvcm9UUUxPVXc) & [Dutch(f)](https://www.dropbox.com/s/8i6y29f38b7nb5s/nl.tar.gz?dl=0) | nl | 300 | 1G | 50160 |
|[Esperanto(w)](https://drive.google.com/open?id=0B0ZXk88koS2KblhZYmdReE9vMXM) & [Esperanto(f)](https://www.dropbox.com/s/pomn7ozppq3xmi1/eo.tar.gz?dl=0) | eo | 300 | 1G | 50597 |
|[Finnish(w)](https://drive.google.com/open?id=0B0ZXk88koS2KVnFyem4yQkxJUFk) & [Finnish(f)](https://www.dropbox.com/s/ex0ne7rel49wtl2/fi.tar.gz?dl=0) | fi | 300 | 467M | 30029 |
|[French(w)](https://drive.google.com/open?id=0B0ZXk88koS2KM0pVTktxdG15TkE) & [French(f)](https://www.dropbox.com/s/iz3qo3cwbba0qfz/fr.tar.gz?dl=0) | fr | 300 | 1G | 50130 |
|[German(w)](https://drive.google.com/open?id=0B0ZXk88koS2KLVVLRWt0a3VmbDg) & [German(f)](https://www.dropbox.com/s/jy6taiacmptr537/de.tar.gz?dl=0) | de | 300 | 1G | 50006 |
|[Hindi(w)](https://drive.google.com/open?id=0B0ZXk88koS2KZkhLLXJvbXVhbzQ) & [Hindi(f)](https://www.dropbox.com/s/pq50ca4o3phi9ks/hi.tar.gz?dl=0) | hi | 300 | 323M | 30393 |
|[Hungarian(w)](https://drive.google.com/open?id=0B0ZXk88koS2KX2xLamRlRDJ3N1U) & [Hungarian(f)](https://www.dropbox.com/s/jtshcott8othxf2/hu.tar.gz?dl=0) | hu | 300 | 692M | 40122 |
|[Indonesian(w)](https://drive.google.com/open?id=0B0ZXk88koS2KQWxEemNNUHhnTWc) & [Indonesian(f)](https://www.dropbox.com/s/9vabe1vci7cnt57/id.tar.gz?dl=0) | id | 300 | 402M | 30048 |
|[Italian(w)](https://drive.google.com/open?id=0B0ZXk88koS2KTlM3Qm1Ta2FBaTg) & [Italian(f)](https://www.dropbox.com/s/orqfu6mb9cj9ewr/it.tar.gz?dl=0) | it | 300 | 1G | 50031 |
|[Japanese(w)](https://drive.google.com/open?id=0B0ZXk88koS2KMzRjbnE4ZHJmcWM) & [Japanese(f)](https://www.dropbox.com/s/7digqy9ag3b9xeu/ja.tar.gz?dl=0) | ja | 300 | 1G | 50108 |
|[Javanese(w)](https://drive.google.com/open?id=0B0ZXk88koS2KVVNDS0lqdGNOSGM) & [Javanese(f)](https://www.dropbox.com/s/a9kmi5r7lr35kji/jv.tar.gz?dl=0) | jv | 100 | 31M | 10019 |
|[Korean(w)](https://drive.google.com/open?id=0B0ZXk88koS2KbDhXdWg1Q2RydlU) & [Korean(f)](https://www.dropbox.com/s/stt4y0zcp2c0iyb/ko.tar.gz?dl=0) | ko | 200 | 339M | 30185 |
|[Malay(w)](https://drive.google.com/open?id=0B0ZXk88koS2KelpKdHktXzlNQzQ) & [Malay(f)](https://www.dropbox.com/s/nl3ljdgxsgbsm6l/ms.tar.gz?dl=0) | ms | 100 | 173M | 10010 |
|[Norwegian(w)](https://drive.google.com/open?id=0B0ZXk88koS2KOEZ4OThyS3gxZHM) & [Norwegian(f)](https://www.dropbox.com/s/mag6beltx2q23aa/no.tar.gz?dl=0) | no | 300 | 1G | 50209 |
|[Norwegian Nynorsk(w)](https://drive.google.com/open?id=0B0ZXk88koS2KOWdOYk5KaVhrX2c) & [Norwegian Nynorsk(f)](https://www.dropbox.com/s/1qsywdv3zqybklm/nn.tar.gz?dl=0) | nn | 100 | 114M | 10036 |
|[Polish(w)](https://drive.google.com/open?id=0B0ZXk88koS2KbFlmMy1PUHBSZ0E) & [Polish(f)](https://www.dropbox.com/s/cibxhnsqk6gn1d8/pl.tar.gz?dl=0) | pl | 300 | 1G | 50035 |
|[Portuguese(w)](https://drive.google.com/open?id=0B0ZXk88koS2KRDcwcV9IVWFTeUE) & [Portuguese(f)](https://www.dropbox.com/s/nl7l8kqky0x94cv/pt.tar.gz?dl=0) | pt | 300 | 1G | 50246 |
|[Russian(w)](https://drive.google.com/open?id=0B0ZXk88koS2KMUJxZ0w0WjRGdnc) & [Russian(f)](https://www.dropbox.com/s/0x7oxso6x93efzj/ru.tar.gz?dl=0) | ru | 300 | 1G | 50102 |
|[Spanish(w)](https://drive.google.com/open?id=0B0ZXk88koS2KNGNrTE4tVXRUZFU) & [Spanish(f)](https://www.dropbox.com/s/irpirphmieg4klv/es.tar.gz?dl=0) | es | 300 | 1G | 50003 |
|[Swahili(w)](https://drive.google.com/open?id=0B0ZXk88koS2Kcl90XzBYZ0lxMkE) & [Swahili(f)](https://dl.dropboxusercontent.com/u/42868014/wordvectors/fasttext/models/sw.tar.gz) | sw | 100 | 24M | 10222 |
|[Swedish(w)](https://drive.google.com/open?id=0B0ZXk88koS2KNk1odTJtNkUxcEk) & [Swedish(f)](https://www.dropbox.com/s/7tbm0a0u31lvw25/sw.tar.gz?dl=0) | sv | 300 | 1G | 50052 |
|[Tagalog(w)](https://drive.google.com/open?id=0B0ZXk88koS2KajRzX2VuYkVtYzQ) & [Tagalog(f)](https://www.dropbox.com/s/4dm7k4sq43dqovx/tl.tar.gz?dl=0) | tl | 100 | 38M | 10068 |
|[Thai(w)](https://drive.google.com/open?id=0B0ZXk88koS2KV1FJN0xRX1FxaFE) & [Thai(f)](https://www.dropbox.com/s/xj1ujw3es0umvzh/th.tar.gz?dl=0) | th | 300 | 696M | 30225 |
|[Turkish(w)](https://drive.google.com/open?id=0B0ZXk88koS2KVDNLallXdlVQbUE) & [Turkish(f)](https://www.dropbox.com/s/9v6h6mz3dv5xgsh/tr.tar.gz?dl=0) | tr | 200 | 370M | 30036 |
|[Vietnamese(w)](https://drive.google.com/open?id=0B0ZXk88koS2KUHZZZkVwd1RoVmc) & [Vietnamese(f)](https://www.dropbox.com/s/7de79czdc85pe8u/vi.tar.gz?dl=0) | vi | 100 | 74M | 10087 |

## License

```text
Word Vector Models
Copyright (c) 2018 Kyubyong Park, Astro

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

