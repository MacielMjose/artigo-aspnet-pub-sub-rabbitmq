# Implementando Publish-Subscribe com ASP.NET Core, RabbitMQ e Docker  

<a href="https://www.luisdev.com.br/2023/01/01/implementando-publish-subscribe-com-asp-net-core-rabbitmq-e-docker/" target="_blank">Link do artigo</a>

Este código-fonte contém o exemplo apresentado no artigo acima, demonstrando o padrão Publish-Subscribe com RabbitMQ.

Para executar o RabbitMQ, junto com sua UI, com Docker:  
`docker run -d --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3-management`

## Projetos
- **AwesomeShop.Customers:** será o publisher
- **AwesomeShop.Notifications:** será um dos subscribers
- **AwesomeShop.Sales:** será um dos subscribers  
