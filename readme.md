# 🧬 Proteins AI-Saturdays 🧬
Code for the proteins properties prediction for the AI Saturdays Murcia

## Pasos

1. Con datasets pequeños -> Entrenar de forma no supervisada (sólo las secuencias)
    - Redes recurrentes -> Predecir el siguinete aminoácido (ver ULMFiT)
    - Transformers -> Predecir el aminoacido oculto (ver BERT)
    - Transformers -> Predecir si amonoácido real o no (ver ELECTRA)
    - Comparar cuales son los mejores modelos.
    - Hecer exploratorio con reducción dimensional.
    - Introducir los datos de los dominios.
2. Con datasets pequeños -> Entrenar de forma supervisada (alguna tarea de clasificación de la proteina)
    - ¿Qué es interesante predecir? Preguntar a Alvaro y Estaban.
3. Repetir lo anterior con datasets más grandes

## Data



| Dataset 26/2/2020        | Num seqs.       | Comprimido | Descompr.     | Descripción                              |
|:------------------------:|----------------:|-----------:|--------------:|------------------------------------------|
| UniProtKB **Varsplic**   | **40.255**      | 8 MB       | **28** MB     | Para pruebas pequeñas                    |
| UniProtKB **Swissprot**  | **561.911**     | 85 MB      | **264** MB    | Manually annotated and reviewed          |
| UniProtKB **TrEMBL**     | **177.754.527** | 39.2 GB    |               | Automatically annotated and not reviewed |
| **UniRef50**             | **39.178.216**  | 7.3 GB     |               | Hasta 50% de similaridad.                |
| **UniRef90**             | **107.153.647** | 23.1 GB    |               | Hasta 90% de similaridad.                |
| **UniRef100**            | **216.491.817** | 51.1 GB    |               | Todas.                                   |
| **UniParc**              | **310.472.414** | 62.3 GB    |               | Todo de todo.                            |

- Enlaces
  - **UniProtKB**: ftp://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/
  - **UniRef**: ftp://ftp.uniprot.org/pub/databases/uniprot/current_release/uniref/
  - **UniParc**: ftp://ftp.uniprot.org/pub/databases/uniprot/current_release/uniparc/


## Deep Learning papers
Modelos de Deep Learning a probar

- **Recurrent**:
  - [ ] Simple RNN
  - [ ] GRU
  - [ ] LSTM
    - Con [DropConnect](https://es.coursera.org/lecture/competitive-data-science/hyperparameter-tuning-iii-Hg3xw)
  - [ ] mLSTM
  - [ ] [AWD-LSTM](https://arxiv.org/abs/1708.02182): Regular LSTM with extra dropouts. Used in [ULMFiT](https://arxiv.org/abs/1801.06146)
  - [ ] [QRNN](https://arxiv.org/abs/1611.01576): Quasi-Recurrent Neural Networks. Used in [MultiFiT](https://arxiv.org/abs/1909.04761)
- **Transformers**:
  - [ ] Attention: [paper](https://arxiv.org/abs/1706.03762), [vídeo](https://youtu.be/iDulhoQ2pro) (Jun 2017)
  - [ ] BERT:      [paper](https://arxiv.org/abs/1810.04805), [vídeo](https://youtu.be/-9evrZnBorM) (Oct 2018)
  - [ ] Transformer-XL: [paper](https://arxiv.org/abs/1901.02860)  (Ene 2019)
  - [ ] XLNet:    [paper](https://arxiv.org/abs/1906.08237), [vídeo](https://youtu.be/H5vpBCLo74U) (Jun 2019)
  - [ ] RoBERTa:  [paper](https://arxiv.org/abs/1907.11692), [vídeo](https://youtu.be/-MCYbmU9kfg) (Jul 2019)
  - [ ] BART:     [paper](https://arxiv.org/abs/1910.13461) (Oct 2019)
  - [ ] Reformer: [paper](https://arxiv.org/abs/2001.04451), [vídeo](https://youtu.be/i4H0kjxrias), [vídeo2](https://youtu.be/Kf3x3lqf9cQ) (Ene 2020)
  - [ ] ELECTRA:  [paper](https://openreview.net/pdf?id=r1xMH1BtvB) (Feb 2020)
  

## Biology Papers

## Biology Papers

- **3D shape** of the protein
  - [Ultra-Deep Learning Model](https://arxiv.org/abs/1609.00680) (2016)
  - Protein secondary structure detection (Jul 2019)
  - [AlphaFold](https://deepmind.com/blog/article/AlphaFold-Using-AI-for-scientific-discovery): From seq -> predict 3D shape
    - [Paper in Nature](https://www.nature.com/articles/s41586-019-1923-7.epdf?author_access_token=Z_KaZKDqtKzbE7Wd5HtwI9RgN0jAjWel9jnR3ZoTv0MCcgAwHMgRx9mvLjNQdB2TlQQaa7l420UCtGo8vYQ39gg8lFWR9mAZtvsN_1PrccXfIbc6e-tGSgazNL_XdtQzn1PHfy21qdcxV7Pw-k3htw%3D%3D) (Ene 2020)
    - [Paper in Proteins](https://onlinelibrary.wiley.com/doi/epdf/10.1002/prot.25834) (Sep 2019)
- **Sequence** of aminoacids of protein
  - [DeepDom](https://psb.stanford.edu/psb-online/proceedings/psb19/jiang.pdf): Predict protein domain boundaries (Ene 2019) `LSTM`
  - UniRep: Detect protein properties (Ma 2019) `mLSTM` `Unsupervised`
  - [Biological Structure and Function Emerge ...](https://www.biorxiv.org/content/10.1101/622803v1)  (Abr 2019, FAIR) `Transformer` `Unsupervised` ⭐
  - [UDSMProt](https://www.biorxiv.org/content/10.1101/704874v2.full.pdf): Detect protein properties (Sep 2019) `AWD-LSTM` `Unsupervised` ⭐
  - [ProGen](https://twitter.com/RichardSocher/status/1237842037744910336) (Mar 2020)  `Transformer` `Unsupervised`  ⭐⭐
    - [Blog](https://blog.einstein.ai/progen/)
    - [Paper](https://www.biorxiv.org/content/10.1101/2020.03.07.982272v1)
- GAN:
  - [ProteinGAN](https://www.biorxiv.org/content/10.1101/789719v2) (Oct 2019)
