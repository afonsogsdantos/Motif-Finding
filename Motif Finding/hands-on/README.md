# Motif Finding
## Motif Finding na resposta ao stress em *S. cerevisiae*
#### Assignment for the Algorithms for the Analysis of Biological Sequences Class, 2ºYear, 2ºSemester, Bachelor in Bioinformatics.
---
Este repositório contém o material prático para o projeto 'Motif Finding' focado em **Motifs Regulatórios na resposta ao stress em S. cerevisiae**. O objetivo é identificar e validar elementos de resposta ao stress (STRE e HSE) nas regiões promotoras de genes da levedura *Saccharomyces cerevisiae*, utilizando algoritmos de descoberta e bibliotecas específicas.

## Setup Local

```bash
# 1. Aceder ao repositório
https://github.com/afonsogsdantos/Motif-Finding

# 2. Entrar na pasta
cd hands_on

# 3. Instalar dependências
pip install numpy matplotlib pandas biopython seaborn 

# Nota: 
É necessário fazer download da pasta hands-on para os ficheiros posteriores (promoters.fasta, meme.xml, motifs_logos.png, resposta_biologica.png) serem guardados na mesma.
```

## Dados do Projeto

O workflow utiliza sequências promotoras (500 bp a montante do codão de iniciação) de genes envolvidos na resposta ao stress em *S. cerevisiae*, extraídas diretamente do NCBI Nucleotide.

| Gene | Principal Regulador | Função Biológica |
| :--- | :--- | :--- |
| *HSP104* | HSF1 | Disagregase de proteínas (Heat Shock) |
| *SSA1* | HSF1 | Chaperona Hsp70 (Heat Shock) |
| *HSP26* | MSN2/4 | sHSP, proteção contra agregação (Stress Geral) |
| *CTT1* | MSN2/4 | Catalase T, defesa oxidativa (Stress Geral) |
| *HSP12* | MSN2/4 | Estabilização de membranas (Stress Geral) |
| *DDR2* | MSN2/4 | Resposta a danos no DNA (Stress Geral) |

## Estrutura do Notebook

```text
 NCBI Entrez (BioPython)
      ↓
 Passo 1 — Extração de Promotores    →  promoters.fasta
      ↓
 Passo 2 — Procura Manual            →  Verificação de STRE e HSE conhecidos
      ↓
 Passo 3 — Descoberta de novo        →  MEME Suite Web Server (Gera meme.xml)
      ↓
 Passo 4 — Parsing do Output         →  Bio.motifs (Leitura do meme.xml)
      ↓
 Passo 5 — Resposta Biológica        →  Validação funcional (Gasch et al. (2000))
 
```

## Algoritmos e Ferramentas Abordados

| Ferramenta / Algoritmo | Descrição |
| :--- | :--- |
| **MEME (Expectation-Maximization)** | Algoritmo iterativo para descoberta de motifs em sequências não alinhadas. |
| **Modelos de Distribuição** | OOPS, ZOOPS e ANR (Any Number of Repetitions) para modelar a ocorrência de motifs. |
| **BioPython (`Bio.motifs`)** | Parsing automatizado de ficheiros XML e manipulação de Position Frequency Matrices (PFMs). |

## Motivação Biológica — Tópicos para Investigação
1. Gasch, A. P. et al. (2000). Genomic expression programs in the response of yeast cells to environmental changes. *Molecular Biology of the Cell*.
2. Schmitt, A. P., & McEntee, K. (1996). Msn2p, a zinc finger DNA-binding protein, is a component of the general stress response machinery in *S. cerevisiae*. *PNAS*.
3. Bailey, T. L., & Elkan, C. (1994). Fitting a mixture model by expectation maximization to discover motifs in biopolymers. *ISMB*.
4. Bailey, T. L. et al. (2015). The MEME Suite. *Nucleic Acids Research*.
5. *Apontamentos e material de apoio da UC de Algoritmos para a Análise de Sequências Biológicas* [Moodle]. FCUP, 2025/26.

### Autores
* Afonso Santos
* Joana Borges
* Rafael Santos