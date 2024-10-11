# Filtering-Stopwords-remover-dalam-NLP
Filtering Stopwords dalam NLP, Python

- Kode NLTK
```python
import nltk
nltk.download('punkt_tab')
nltk.download('stopword')
import string
from nltk.tokenize import sent_tokenize, word_tokenize
from nltk.corpus import stopwords
kalimat = "Cuaca hari ini sangat cerah dan menyenangkan untuk berolahraga."
kalimat = kalimat.translate(str.maketrans('','',string.punctuation)).lower()

tokens = word_tokenize(kalimat)
listStopword = set(stopwords.words('indonesian'))

removed = []
for t in tokens:
    if t not in listStopword:
        removed.append(t)

print(removed)
```
hasil = ['cuaca', 'cerah', 'menyenangkan', 'berolahraga']
  
- Kode NLTK Sastrawi
```python
import string
from Sastrawi.StopWordRemover.StopWordRemoverFactory import StopWordRemoverFactory
from nltk.tokenize import word_tokenize
import nltk
nltk.download('punkt_tab')
nltk.download('stopwords')

factory = StopWordRemoverFactory()
stopword = factory.create_stop_word_remover()
kalimat = "Cuaca hari ini sangat cerah dan menyenangkan untuk berolahraga."
kalimat = kalimat.translate(str.maketrans('','',string.punctuation)).lower()
stop = stopword.remove(kalimat)
tokens = nltk.tokenize.word_tokenize(stop)
print(tokens)
```
hasil = ['cuaca', 'cerah', 'menyenangkan', 'berolahraga']


# Tugas
Komentar pengguna disimpan dalam file PDF. Tugas Anda adalah memproses komentar-komentar tersebut, melakukan filtering dengan menghapus stopwords menggunakan NLTK dan Sastrawi, dan kemudian menyimpan hasilnya dalam file .txt.

- Kode Filtering NLTK
[File Python](https://github.com/DeanAdriansyah/Filtering-Stopwords-remover-dalam-NLP/blob/main/filtering_NLTK), dan Hasil nya [hasil](https://github.com/DeanAdriansyah/Filtering-Stopwords-remover-dalam-NLP/blob/main/hasil_bersih_stopwords.txt)

- Kode Filtering NLTK Sastrawi
[File Python](https://github.com/DeanAdriansyah/Filtering-Stopwords-remover-dalam-NLP/blob/main/filtering_sastrawi), dan Hasil nya [hasil](https://github.com/DeanAdriansyah/Filtering-Stopwords-remover-dalam-NLP/blob/main/hasil_bersih_sastrawi.txt)

