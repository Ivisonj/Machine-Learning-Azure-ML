# Machine-Learning-Azure-ML
Criação de um modelo com previsão usando o Azure-ML

Links úteis:

[Explore Azure AI Services](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html)

[Explore Automated Machine Learning in Azure Machine Learning](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)

[Fonte dos dados](https://aka.ms/bike-rentals)

## Passo 1: Criando recurso do Azure Machine Learning

O Primeiro passo foi criar um recurso de Machine Learning. Para isso, cliquei em "Criar recurso" e depois pesquisei por Azure Machine Learning.

## Passo 2: Configuração recurso de Machine Learning

Na próxima foi etapa preenchi algumas configurações, como: grupo de recursos e detalhes sobre a área de trabalho. 

Em seguida, criei o recurso e cliquei no boão "ir para recurso". 

## Passo 3

Depois das configurações da area de trabalho de machine learning,  cliquei no botão "iniciar o estúdio"

Logo após, no menu lateral, cliquei na opção "ML automatizado" e em seguida cliquei em "Novo trabalho de ML automatizado".

Em "Configurações básicas", preenchi os campos "Nome do trabalho", "Novo nome do experimento" e coloquei uma descrição. 

No passo "Tipo de tarefa e dados", selecionei o tipo de tarefa como Regressão e em seguida, em "Selecionar dados".  Nesse momento tive que preencher os campos "Nome", "Descrição" e "Tipo". No próximo passo "Fonte de dados", escolhi "De arquivos da Web". 

Em seguida, informei a URL https://aka.ms/bike-rentals de dados para treinamento do modelo. 

No passo "Configurações", mantive as configurações padrão, com excessão do campo "Cabeçalhos de coluna" que preenchi com a opção "Somente o primeiro arquivo tem cabeçalhos".

Logo após, os dados foram carregados eu eu cliquei em "criar". 

Em "Configurações de tarefas", escolhi o conjunto de dados importado. Após, em "Coluna de destino" escolhi a coluna rentals.

Nos campos de "Limite", preenchi com os valores abaixo e marquei "Habilitar encerramento antecipado".

Em "Validar e testar", em "Tipo de validação" escolhi "Divisão de validação de treinamento".

Ao avançar, em Computação, mantive os valores mostrados na imagem abaixo.

Após avançar e examinar as configurações do trabalho, cliquei em "Enviar trabalho de treinamento".

Após finalizar o trabalho de treinamento, o modelo fica acessível na opção de menu "Modelo".

## Passo 4: Métricas do modelo

Para acessar as métricas do modelo treinado, na página do modelo, acesso o link informado em "Criado por trabalho". Também é possível acessar o trabalho informado na opção do menu "Tarefas (jobs)".

Na página da tarefa, acessei a aba métricas.

## Passo 5: Teste do modelo

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
