# Promise-
Promise+ é uma expansão da base de Requisitos de Software Promise_exp. Bases de requisitos podem ajudar na criação de modelos de classificação automática de requisitos. O dataset contém requisitos em inglês e as classes contidas na Promise+ são: F(Functional), A (Availability), L (Legal), LF (\Look and Feel), MN (Maintainability), O (Operacional), PE (Performance), SC (Scalability), US (Usability), FT (Fault Tolerance) e PO (Portability).

A Promise+ foi construída seguindo os princípios orientadores da primeira expansão (PROMISE_exp). Após busca na web foram selecionados 42 documentos de requisitos de software. Esses documentos tiveram seus requisitos analisados por seis especialistas. A fim de atestar a classificação, cinco especialistas tiveram sua classificação comparada ao sexto especialista. Desta comparação foi retirado o índice de kappa.

A imagem abaixo apresenta os detalhes da metodologia:

![Metodologia da Base Fluxo](https://github.com/user-attachments/assets/4caa0d20-bf41-4bd0-bad0-0c8a5091336a)

A Promise+ significou um grande aumento quantitativo nos dados, conforme demonstrado na tabela abaixo:

![Comparação quantitativa entre as bases](https://github.com/user-attachments/assets/450a0717-d378-4e12-aad4-a24a04addc3e)

De forma a aumentar o conhecimento sobre os documentos de requisitos de software acrescentados, foi realizada uma análise quanto ao tipo de software.Foram utilizadas 
as seguintes classificações de software: sistema, aplicativo, científico/de engenharia, embarcado, linha de produtos, web e inteligência artificial. No arquivo "Lista dos tipos de software.xlsx" cada tipo de software está vinculado ao id do documento de requisito. O gráfico abaixo demonstra a distribuição desses diferentes tipos:

![chart(2)](https://github.com/user-attachments/assets/370e8ee4-20e5-4d27-acaf-e7f239e653a6)

Outra análise feita foi sobre o documento de requisitos ser de um um software da academia ou da indústria, sendo 18 da academia e 24 da indústria.

No arquivo Promise+.arff está o arquivo feito na ferramenta weka. Neste arquivo tem-se todos os requisitos, a lista de id de projetos da indústria, a lista de id de projetos da academia e o rótulo de cada requisito. No arquivo Promise+.csv, tem-se somente o texto dos requisitos e o rótulo.

Para fins de citação, a Promise+ também está hospedada no Zenodo, sob o seguinte DOI: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.12805484.svg)](https://doi.org/10.5281/zenodo.12805484)
