# package_model

Istruzioni per creare un modulo Python e condividerlo con *pip install [package_model]*.

(fonte utilizzata: https://www.youtube.com/watch?v=FkmtmYFTlYE)

# 1) Creazione di un pacchetto python e installazione locale 

Creare la seguente struttura ad albero:

```
package_model/
├── LICENSE
├── package_model
│   ├── example.py
│   └── __init__.py
├── README.md
└── setup.py
```

Il file *setup.py* sarà il file che Pip andrà a leggere quando eseguiremo l'istallazione del pacchetto e contiene le seguenti istruzioni:

```
from setuptools import setup

setup(name='package_model',
      version=0.1,
      description='Compute the square of a number',
      author='Lorenzo Marini',
      packages=['package_model'],
      zip_safe=False)

```

Passiamo adesso al file *__init__.py*. Al suo interno scriviamo:

```
from .example import quadrato
```

In questo modo, saremo ingrado di importale le singole funzioni (in questo caso solo una: 'quadrato') del nostro modulo *exmaple.py*

Adesso, siamo pronti per installare il nostro pacchetto localmente sul nostro computer.
Per fare ciò, dobbiamo semplicemente lanciare il seguente comando:

```
pip install .
```

NB: da lanciare dalla cartella principale del pacchetto (in cui è presente il file *setup.py*).

Vediamo l'output:
```
lorenzomarini@lorenzomarini-MacBookPro:~/Desktop/package_model$ pip install .
Defaulting to user installation because normal site-packages is not writeable
Processing /home/lorenzomarini/Desktop/package_model
  Preparing metadata (setup.py) ... done
Building wheels for collected packages: package-model
  Building wheel for package-model (setup.py) ... done
  Created wheel for package-model: filename=package_model-0.1-py3-none-any.whl size=13830 sha256=c136a22a940ad2fb620893b33d8773964c62772ca34fbe40bdbf5bc3b2c47548
  Stored in directory: /tmp/pip-ephem-wheel-cache-p3gp0w1j/wheels/d6/1a/c0/6e22efdbc48c105b11d87f65f2062245a1a801b8b91f0c5711
Successfully built package-model
Installing collected packages: package-model
Successfully installed package-model-0.1
```
Abbiamo installato il nostro package sul nostro computer!

Per essere sicuri che tale pacchetto sia installato e salvato tra i vari pacchetti, diamo il comnado:

```
pip list
```
e verifica che *package_model* sia all'interno della lista.

# 2) Caricamento del pacchetto sul repositorio PyPi

Ora comincia la parte più eccitante...
Siamo pronti per caricare il nostro package nel repositorio di **PyPi**

NB: ci sono 2 repositori di nostro interesse.

Essi sono:
- **PyPi** per il testing (https://test.pypi.org/manage/projects/)
- il repositorio **PyPi** regolare (https://pypi.org/manage/projects/)

Attenzione: i due repositorio non sono la stessa cosa. Ciascuno ha il proprio account

Per caricare il pacchetto, dobbiamo prima altri file: **licence.txt**, **setup.cfg** e **README.md**.

Questi tre file addizionali sono necessari per poter caricare il nostro pacchetto su PuPi.







# 3) Pubblicazione del pacchetto