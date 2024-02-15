# Machine-Learning-Azure-ML
Criação de um modelo com previsão usando o Azure-ML

Links úteis:

[Explore Azure AI Services](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html)

[Explore Automated Machine Learning in Azure Machine Learning](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)

[Fonte dos dados](https://aka.ms/bike-rentals)

## Passo 1: 

O Primeiro passo foi criar um recurso de Machine Learning. Para isso, cliquei em "Criar recurso" e depois pesquisei por Azure Machine Learning.

## Passo 2: 

Nessa etapa preenchi alguns campos sobre machine learning workspace. No input "Resource group" preenchi com o nome "LABAI-900", no "Name" escolhi o nome "laboratorioai900", a "Region" usei "East US" e os demais inputs e configurações mantive o padrão criado pela plataforma. 

Em seguida, criei o recurso e cliquei no boão "ir para recurso". 

## Passo 3:

Depois das configurações da area machine learning workspace,  cliquei no botão "iniciar o estúdio". 

Logo após, no menu lateral, cliquei na opção "ML automatizado" e em seguida cliquei em "Novo trabalho de ML automatizado".

Em "Configurações básicas", preenchi os campos "Nome do trabalho" com o nome "mslearn-bike-automl", em "Novo nome do experimento"  usei "mslearn-bike-rental" e também preenchi o campo "Dscrição. 

Em "Tipo de tarefa e dados", selecionei o tipo de tarefa como "Regressão" e, em seguida, nas configurações "Selecionar dados", tive que preencher os campos "Nome" com o valor "alugueldebicicletas" e também preenchi o input de "Descrição" e "Tipo" como "Tabular". No próximo passo, em "Fonte de dados", escolhi "De arquivos da Web". 

Em seguida, informei a URL "https://aka.ms/bike-rentals" de dados para treinamento do modelo. 

No passo "Configurações", mantive as configurações padrão, com excessão do campo "Cabeçalhos de coluna" que preenchi com a opção "Somente o primeiro arquivo tem cabeçalhos".

Logo após, os dados foram carregados eu eu cliquei em "criar". 

Em "Configurações de tarefas", escolhi o conjunto de dados importado. Após, em "Coluna de destino" escolhi a coluna rentals.

Nas configurações adicionais, mantive as configurações padrões em "Métrica primária", mas em modelos permitidos selecionei "RandomForest" e "LightGBM".

Nos campos de "Limite", preenchi com os campos "Máximo de avaliações", "Máximo de avaliações simultâneas" e "Máximo de nós" com o valor "3". Em "Limite de pontuação da métrica", usei "0,085". Nas opções "Tempo limite do experimento" e "Tempo limite de iteração", escolhi o vlaor "15", além de marcar a opção "Habilitar encerramento antecipado"

Em "Validar e testar", na opção "Tipo de validação" escolhi "Divisão de validação de treinamento".

Avancei, em Computação, mantive os valores.

Ao avançar e examinar as configurações do trabalho, cliquei em "Enviar trabalho de treinamento".

Após finalizar o treinamento, o modelo ficou disponível na opção de menu "Modelo".

## Passo 4: 

Para acessar as métricas do modelo treinado, na página do modelo, acesso o link informado em "Criado por trabalho". Também é possível acessar o trabalho informado na opção do menu "Tarefas (jobs)".

Na página da tarefa, acessei a aba métricas.

## Passo 5:

Na página do modelo, cliquei na aba "Pontos de extremidade". Também é possível acessar pelo menu lateral em "Pontos de extremidade". Cliquei no ponto correspondente ao modelo gerado. Em seguida, acessei a aba "Testar".

Para o teste, utilizei o json abaixo:

<code>
{
  "input_data": {
    "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]
  }
}
</code>
