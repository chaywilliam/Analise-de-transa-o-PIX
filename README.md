# Introdução

Neste Case de análise de dados financeiros utilizando a ferramenta Spark. O objetivo é demonstrar o processo completo, desde a coleta e preparação dos dados até a modelagem, avaliação e implantação de um modelo de machine learning para detecção de fraudes.

## Serão abordados os seguintes tópicos:


* Coleta e entendimento dos dados * 
* Pré-processamento com Spark
* Análise Exploratória de Dados
* Modelagem de Machine Learning
* Avaliação do Modelo
* Implantação e Ações

O caso simula uma situação real de análise de transações financeiras de um cliente de um banco, com o objetivo de entender seus padrões de transações, identificar tentativas de fraude e sugerir ações para melhorar sua experiência.

# Coleta e Entendimento dos Dados

O primeiro passo é coletar os dados que serão analisados. Neste caso, estamos trabalhando com dados de extrato bancário simulados de um cliente chamado Jonathan Gonçalves.

Os dados contêm informações como data e hora da transação, valor, descrição, categoria (transferência, pagamento, etc), banco origem, banco destino e uma coluna indicando se a transação é fraudulenta ou não.

É importante conhecer e entender bem os dados que estão sendo analisados, através de uma amostragem e verificação de cada coluna:


Data: data e hora da transação
Valor: valor monetário da transação
Descrição: descrição da transação
Categoria: tipo/categoria (transferência, pagamento, etc)
Banco Origem: banco de origem do valor transacionado
Banco Destino: banco de destino do valor transacionado
Fraude: indica se a transação é fraudulenta (Sim ou Não)

Com esse entendimento inicial já é possível começar a pensar em algumas análises, como: padrões de transações ao longo do tempo, principais categorias, bancos mais utilizados, distribuição dos valores, entre outras.

# Pré-processamento com Spark

Com os dados coletados, a próxima etapa é o pré-processamento utilizando a ferramenta Spark. Nesta etapa são realizadas tarefas como:


Limpeza de dados: tratamento de valores nulos, dados duplicados, conversão de tipos de dados, etc.
Transformação de dados: criação de novas colunas analíticas, mudança de formatos, extração de novos atributos, etc.
Análise exploratória inicial: entendimento das distribuições, estatísticas descritivas, visualizações, etc.

Alguns insights obtidos nesta etapa para os dados do nosso cliente Jonathan:


Possui um alto volume de transações: mais de 2000 transações em 2 anos
Valores de transações variam bastante, de R$ 2 a R$ 200 mil
Existem transações fraudulentas (15% do total)
A maioria das transações são transferências bancárias

Essas primeiras análises já permitem entender um pouco melhor o perfil das transações do cliente e identificar algumas oportunidades de melhoria, como investigar as transações fraudulentas.

# Análise Exploratória de Dados

Após o pré-processamento, podemos mergulhar em uma análise mais profunda através da Análise Exploratória de Dados, buscando entender melhor os dados e extrair insights. Algumas análises realizadas:

Distribuição temporal das transações: há picos de até 50 transações por mês, indicando um alto volume de transações mensais.

Principais categorias: Transferências bancárias representam 75% das transações, indicando que essa é a categoria mais comum.

Valores das transações: 50% das transações são abaixo de R$ 5 mil, 25% até R$ 19 mil. Valores acima de R$ 20 mil são outliers e pouco comuns.

Bancos mais frequentes: os dois bancos mais utilizados são Banco do Brasil e BTG. Porém o volume transacionado com o BTG é menor.

Transações fraudulentas: correspondem a 15% do total de transações. Todas as tentativas de fraude identificadas são em valores acima de R$ 19,9 mil.

Esses insights já permitem tirar algumas conclusões sobre o comportamento do cliente e identificar padrões nas transações fraudulentas, por exemplo.

# Modelagem de Machine Learning

Com o entendimento dos dados, podemos criar um modelo de machine learning para detectar transações fraudulentas e classificá-las automaticamente.

A técnica escolhida foi uma Random Forest, um algoritmo de ensemble que combina o resultado de várias árvores de decisão.

As variáveis ou atributos utilizados para treinar o modelo foram:


(-) Valor da transação
(-) Banco de origem
Banco de destino
Categoria da transação
Hora do dia
Dia da semana

Após o treinamento, o modelo obteve uma acurácia de 95% na detecção de fraudes na base de validação. Isso significa que ele é capaz de identificar transações fraudulentas com confiabilidade para poder tomar decisões.

# Avaliação do Modelo

Antes de aplicar o modelo é preciso avaliar se os resultados fazem sentido e se ele realmente responde às necessidades de negócio. Algumas verificações realizadas:


O modelo identifica corretamente transações acima de R$ 20 mil como fraudulentas? Sim
Ele consegue responder quais são os bancos e categorias mais utilizados? Sim
A acurácia de 95% atende ao mínimo exigido? Sim

O modelo desenvolvido atende às expectativas e necessidades do negócio. Portanto, podemos prosseguir para a implantação e uso nas operações diárias.

# Implantação e Ações

Com o modelo validado, ele pode ser implantado para uso em produção, aplicando as predições de fraude em tempo real durante as transações.

Algumas ações sugeridas com base nas análises:


Diminuir o limite máximo de transferência do cliente para R$ 20 mil, já que este é o valor acima do qual as fraudes ocorrem.

Desenvolver um sistema que utilize o modelo treinado para detectar fraudes antes da transação ser efetivada, bloqueando tentativas suspeitas.

Sugerir ao cliente a utilização de uma conta jurídica, devido ao alto volume e valores de suas transações. Uma conta PJ possui taxas e funcionalidades mais adequadas.

Monitorar continuamente as métricas do modelo em produção.


Dessa forma foi possível entregar um projeto de big data completo, desde a extração de insights à implantação de um modelo de machine learning, trazendo valor real para o negócio e melhor experiência para o cliente do banco.

Esse é um exemplo de caso que simula desafios reais de análise de dados no setor financeiro. Há muitas possibilidades de análises que podem ser realizadas, cabendo ao cientista de dados explorar da melhor forma os dados disponíveis para extrair insights e construir soluções analíticas.

# Conclusão

Este foi um Case prático de análise de transações financeiras utilizando a ferramenta Spark. Por meio das etapas de entendimento, pré-processamento, análise exploratória, modelagem e implantação foi possível extrair insights sobre os dados e construir um modelo de detecção de fraudes.

O caso simula um problema real e reflete como é possível entregar valor de negócio aplicando técnicas de big data e data science. Embora a solução apresentada seja uma entre muitas possibilidades, ela demonstra um fluxo completo desde a extração de insights à aplicação prática dos resultados.

Há muitas possibilidades de análises que podem ser realizadas, cabendo ao cientista de dados explorar os dados disponíveis para extrair o máximo de insights e construir soluções analíticas que gerem valor para o negócio. Este caso serve como um exemplo prático desse processo.
