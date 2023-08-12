# DIAHPhish_Dataset

Esse repositorio detalha a base de daodos aplicada ao trabalho: DIAHPhish: Uma solução baseada em Redes Neurais Siamesas para detecção de ataques homográficos em páginas phishing direcionadas

Resumo: O phishing é um dos mecanismos mais populares para aplicação de golpes virtuais em atividade. Grande parte da eficácia dos ataques de phishing reside em sua capacidade de induzir o usuário a convencê-lo de que está acessando um serviço genuíno. Para tal função, uma parcela significativa dos ataques explora a aplicação de termos homográficos para verificar a confiabilidade do ataque. Neste cenário, o estudo propõe uma abordagem autônoma, baseada em uma rede neural siamesa recorrente LSTM, capaz de identificar a presença de termos homográficos em partes da URL e conteúdo de páginas de phishing. Como resultado, o modelo proposto mostrou-se altamente eficiente na detecção de termos maliciosos, atingindo um índice médio de assertividade superior a 99,50\%.

# Construção do dataset

O processo de construção do dataset pode ser dividido em duas etapas: (A) seleção das marcas participantes e (B) construção dos termos deturpados.

**Para etapa A:** foram selecionadas trinta marcas atuantes no Brasil, tidas como mais populares em uma extração de registro da plataforma mantenedora de listas de bloqueio PhishTank. A tabela seguinte, apresenta as marcas selecionadas, bem como a quantidade de ocorrências por marca-alvo e sua proporção dentro do conjunto de dados.

| # | Marca | Phishes | % | # | Marca | Phishes | % |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 01 | amazon | 4740 | 8.26% | 16 | tsb | 1291 | 2.25% |
| 02 | runescape | 4736 | 8.26% | 17 | yahoo | 1199 | 2.09% |
| 03 | google | 4668 | 8.14% | 18 | magazine luiza | 1186 | 2.07% |
| 04 | facebook | 4463 | 7.78% | 19 | adobe | 1093 | 1.91% |
| 05 | paypal | 4462 | 7.78% | 20 | dhl | 1074 | 1.87% |
| 06 | microsoft | 4335 | 7.56% | 21 | americanas | 1063 | 1.85% |
| 07 | halifax | 3393 | 5.92% | 22 | caixa econômica | 820 | 1.43% |
| 08 | apple | 3234 | 5.64% | 23 |steam | 697 | 1.22% |
| 09 | itau | 2646 | 4.61% | 24 | dropbox | 652 | 1.14% |
| 10 | lloyds | 1745 | 3.04% | 25 | bradesco | 629 | 1.10% |
| 11 | rakuten | 1493 | 2.60% | 26 | banco do brasil | 576 | 1.00% |
| 12 | bank of america | 1446 | 2.52% | 27 | santander | 539 | 0.94% |
| 13 | wellsfargo | 1381 | 2.41% | 28 | alibaba | 455 | 0.79% |
| 14 | ebay | 1350 | 2.35% | 29 | hsbc | 397 | 0.69% |
| 15 | netflix | 1308 | 2.28% | 30 | aol | 285 | 0.50% |

**Para etapa B:** foi desenvolvido um motor capaz de elaborar termos distorcidos (typosquatting) referentes às marcas selecionadas, a partir da aplicação aleatória de 10 comportamento comumente observados em termos homográficos. Estes são:

01. **Inserir letra de tecla vizinha no teclado:** o termo do google para goopgle.
02. **Inserir pluralidade:** por exemplo, o termo do google para googles.
03. **Inserir letra de forma repetida:** o termo do google para gooogle.
04. **Inserir separadores:** por exemplo, o termo “googledrive” por “google-drive” ou “google\drive” ou “google.drive”.
05. **Omitir letra:** por exemplo, o termo google.com por “goole” ou “googl.com”.
06. **Trocar por tecla vizinha no teclado:** o termo google por giogle.
07. **Trocar posição de uma letra:** por exemplo, o termo google para ogogle.
08. **Trocar caractere por semelhança:** por exemplo, o termo do Google para goog1e ou go0gle (substituindo a letra o por, respectivamente, um número 0).
09. **Trocar vogal:** ex. o termo google para gaagle.
10. **Simulação de TLD:** por exemplo, o termo google.com para google-com.tk.
