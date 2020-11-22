# Teste técnico ADDE Sistemas

Este projeto é parte do teste técnico proposto pela ADDE sistemas, no qual o objetivo era desenvolver um sistema contendo frontend
e backend capaz de mostrar o clima atual e a previsão do tempo a partir do input de um cidade e/ou localização do usuário.

## Backend
No backend foi utilizada a tecnologia Python, na versão 3.9 com o framework Flask para: 
* Comunicação com a api externa OpenWeatherMap para pegar os dados de clima filtrado por cidade/região.
* Persistência dos dados recuperados da API por 15 minutos através de cache
* Filtragem dos dados moldando o objeto desejado a ser fornecido para o frontend
* Uso de uma rota exclusiva para recuperar os dados usando localização (latitude e longitude)
* Uso de rota exclusiva para recuperar os dados de previsão de 7 dias, utilizando o nome da Cidade desejada e Região.

## Frontend
No Frontend foi utilizado Typescript junto ao framework Angular 11, com o objetivo de capturar entrada do usuário através de um input, 
e exibir dados recuperados do backend com base nessa entrada. Por padrão a previsão utilizada a localização atual do usuário, fornecida
pelo navegador.
* Foi criado um serviço weather que consome as informações do backend e é usado na aplicação para entregar a informação
* Foi utilizada a tipagem de dados do typescript, onde é recebido um objeto do tipo Weather do backend, que devve estar em conformidade
com os atributos esperados
* Após a consulta pelo backend é exibido para o usuário os dados através da temperatura atual, cidade, clima, e de um indicativo visual.