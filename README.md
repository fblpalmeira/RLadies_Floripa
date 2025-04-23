# [RLadies Floripa](https://www.meetup.com/rladies-florianopolis/)
## Meetup ["Explorando o pacote {pcir} para análise de conflitos e consenso"](https://www.meetup.com/rladies-florianopolis/events/305989838/?eventOrigin=group_upcoming_events)
### [Francesca B. L. Palmeira](https://fblpalmeira.github.io/), francesca@alumni.usp.br 

O conteúdo desta página é referente ao evento ["Explorando o pacote {pcir} para análise de conflitos e consenso"](https://www.meetup.com/rladies-florianopolis/events/305989838/?eventOrigin=group_upcoming_events) oferecido pelas [RLadies Floripa](https://www.meetup.com/rladies-florianopolis/).

O  [`pcir` - Potential for Conflict Index in R](https://fblpalmeira.github.io/pcir/) é um método estatístico descritivo usado para melhorar a compreensão dos resultados em pesquisas de dimensões humanas. O pacote oferece as ferramentas necessárias para calcular, comparar e representar graficamente o potencial de conflito entre grupos de interesse. Os conceitos de consenso e discordância/conflito têm relevância em vários campos, incluindo economia, ciência política, psicologia, sociologia e recursos naturais. Vale a pena notar que, embora o PCI possa ser computado atualmente usando softwares como Excel, SPSS e SAS, não havia nenhum pacote no R dedicado para realizar essa análise específica.

Para mais informações sobre a PCI, visite a página do [Professor Jerry J. Vaske](https://sites.warnercnr.colostate.edu/jerryv/potential-conflict-index/). Nela tem disponível a extensão 
da PCI para ser utilizada no Excel,  SPSS e SAS.

-----

## Criando uma conta no [Posit Cloud](https://posit.cloud/)

Vamos fazer os exercícios utilizando a [linguagem R](https://www.r-project.org/about.html) em uma versão do [RStudio](https://posit.co/download/rstudio-desktop/) que está disponível na nuvem, sem precisar instalar de nenhum programa ou software no computador. 

Primeiro, você deverá criar uma conta pessoal no [Posit Cloud](https://posit.cloud/). O site é seguro e não precisa pagar nada, pois vamos optar pelo plano gratuito. O tutorial abaixo tem o passo a passo para abrir a conta. 

- [Tutorial para abrir uma conta no Posit Cloud `.pdf`](https://github.com/fblpalmeira/pronta_cientista_2024/blob/main/docs/Tutorial_abrir_conta_PositCloud_pronta_2024.pdf)

## Conhecendo o ambiente R

- [Conhecendo o RStudio `.pdf`]():

- [Tutorial para fazer um gráfico de waffle `.pdf`](https://github.com/fblpalmeira/pronta_cientista_2024/blob/main/docs/Tutotial_RStudio_Cloud_Waffle_Pronta_Cientista_2024_05_25.pdf): o código do exercício está dentro dos [links](https://github.com/fblpalmeira/pronta_cientista/blob/main/README.md#links-dos-exerc%C3%ADcios-no-posit-cloud). Caso tenha alguma dúvida sobre o exercício é só seguir o tutorial, nele tem todo o passo a passo de como construir o gráfico da sua biografia e, ao final, exportá-lo para o computador.

## Links dos exercícios no [Posit Cloud](https://posit.cloud/)

A seguir, precisaremos acessar os exercícios clicando em qualquer um dos links abaixo. Dentro de cada link, tem o mesmo material. Como estamos utilizando o plano gratuito, apenas cinco pessoas podem acessar simultaneamente cada link. Caso o primeiro link não funcione, pode ser que tenha mais de cinco pessoas tentando acessar ao mesmo tempo. Quando isso acontecer, tente acesso por qualquer um dos outros links. 

Lembre-se que para fazer os exercícios que estão on-line, você vai precisar ter acesso à internet, abrir uma conta no [Posit Cloud](https://posit.cloud/) e fazer login com o seu email particular, conforme explicado no início deste documento. 

- [Link1 `.R`](https://posit.cloud/content/10231646) 

- [Link2 `.R`](https://posit.cloud/content/10231646)

- [Link3 `.R`]()

- [Link4 `.R`]()

## Material 

No link abaixo, está todo o material deste treinamento incluindo os códigos dos exercícios, as planilhas .xlsx, os tutoriais em .pdf, etc.

- [Material para download]()

## Prática 

O objetivo desta prática é visualizar o Índice Potencial de Conflito (PCI) entre grupos de interesse utilizando dados de entrevistas estruturadas ou questionários. 

## Fluxo de trabalho  

Etapas implementadas no pacote `pcir`:

- Ler os dados de entrada provenientes das entrevistas – ver conjunto de dados de exemplo (Planilha);  
- Contar a frequência das respostas para cada pergunta – ver (Tabela 1);  
- Calcular o PCI para cada pergunta – ver (Tabela 2);  
- Gerar um gráfico de bolhas para visualizar os resultados – ver (Figura).

---

## Usage

```r
# Instala o pacote pcir 
# Só precisa ser instalado na primeira vez que utilizar o pacote
devtools::install_github("fblpalmeira/pcir")

# Abre o pacote pcir
# Precisa ser carregado toda vez que você abrir o arquivo pcir_exercise.R
library(pcir)

# Adiciona os dados brutos (na escala Likert)
df1 <- data.frame(
  A = c(-1, -1, -1, -1, -1),
  B = c(-1, 1, 1, -1, 1),
  C = c(1, 1, 1, 1, -1),
  D = c(-1, -1, 1, 1, 1),
  E = c(1, 1, -1, -1, -1),
  F = c(-1, -1, -1, -1, -1),
  G = c(-1, 1, 1, -1, 1),
  H = c(1, 1, 1, 1, -1)
)

# Conta as frequências de cada categoria
df_count <- counting(df1)
df_count

# Calcula o índice potencial de conflito (PCI)
df_pci <- pci(df_count)
df_pci

# Visualiza o índice por meio de uma gráfico de bolhas
bubble_plot <- bubble(df_pci)
bubble_plot # Display the bubble plot
```

-----

## Bibliografia básica

Manfredo, M., Vaske, J., Teel, T. (2003). [The potential for conflict index: A graphic approach to practical significance of human dimensions research](https://www.tandfonline.com/doi/abs/10.1080/10871200304310). Human Dimensions of Wildlife 8(3), 219-228.

Vaske, J. J., Beaman, J., Barreto, H., Shelby, L. B. (2010). [An extension and further validation of the potential for conflict index](https://www.tandfonline.com/doi/abs/10.1080/01490401003712648). Leisure Sciences 32(3), 240-254.

## Leitura adicional

Bath, A. J., Engel, M. T., van der Marel, R. C., Kuhn, T. S., & Jung, T. S. (2022). [Comparative views of the public, hunters, and wildlife managers on the management of reintroduced bison (Bison bison)](https://www.sciencedirect.com/science/article/pii/S2351989422000178). Global Ecology and Conservation 34, e02015.

Engel, M. T., Vaske, J. J. (2022). [Balancing public acceptability and consensus regarding marine protected areas management using the Potential for Conflict Index2](https://www.sciencedirect.com/science/article/abs/pii/S0308597X22000896). Marine Policy 139, 105042.

Engel, M. T., Vaske, J. J., Bath, A. J., Marchini, S. (2017). [Attitudes toward jaguars and pumas and the acceptability of killing big cats in the Brazilian Atlantic Forest: an application of the Potential for Conflict Index 2](https://link.springer.com/article/10.1007/s13280-017-0898-6). Ambio 46, 604-612.

Palmeira, F. B. L., Trinca, C. T., Haddad, C. M. (2015). [Livestock predation by puma (Puma concolor) in the highlands of a southeastern Brazilian Atlantic Forest](https://link.springer.com/article/10.1007/s00267-015-0562-5). Environmental Management 56, 903-915.
