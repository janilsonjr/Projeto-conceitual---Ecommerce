# Projeto-conceitual---Ecommerce
Resolução do desafio refinamento de um projeto conceitual de Banco de Dados. Neste desafio modelamos um mini-mundo no contexto de um E-commerce. 

O objetivo desse projeto consistia refinar o modelo apresentado acrescentando os seguintes pontos:

1. Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
2. Pagamento – Pode ter cadastrado mais de uma forma de pagamento;
3. Entrega – Possui status e código de rastreio;

O item 1, que trata dos clientes serem pessoas físicas ou jurídicas, foi abordada a generalização para resolver o problema. a entidade `Cliente` é mãe das entidades `Cliente PJ` e `Cliente pf`, com cardinalidade 1 para 1, satisfazendo a restrição de que um cliente não pode ter as duas informações. 

Para o item 2 a abordagem foi a mesma, onde `Pagamento` tornou-se uma entidade fraca de `Cliente` onde as informações das "varias formas de pagamento" registradas, que neste caso se entende como a possibilidade de um cliente registrar varios cartões, foram persistisdas herdando as informações dos clientes que os registraram. a cardinalidade foi de 1 para muitos uma vez que um cliente pode registrar varios cartões. 

o item 3 apenas registrei o código de rastreio como atributo da entidade `Pedidos` e entendi o atributo "Status do pedido" como necessário para persistir as informações de entrega realizada do pedido. Adicionar uma entidade ou atributo para persistir as informações de status de entrega resultariam em redundância uma vez que o atributo ja existente na entidade já é capaz de cobrir todo o ciclo de vida do pedido, desde a realização do pedido, seu processamento e sua entrega. 
