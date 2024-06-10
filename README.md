# festival-de-musica-design

## Objetivo:

- Esboçar protótipo de design de uma plataforma para aquisição de ingressos para eventos.


## Arquitetura:

O sistema contém 3 principais serviços:

1. Serviço de Autenticação: serviço responsável pelo cadastro e autenticação das credenciais de um usuário.
2. Serviço de Fila para Compra de Ingressos: serviço responsável por alocar e gerenciar a posição dos usuários já autenticados em uma fila para compra de ingressos. Caso o evento não possua uma fila aberta ou o evento esteja indisponível, o usuário será notificado. Caso o evento esteja disponível mas não haja filas, o usuário será redirecionado para o ```Serviço de Ingressos```.
3. Serviço de Ingressos: serviço responsável pelo gerenciamento e disponibilização de ingressos. Quando o usuário selecionar ingressos para comprar, será feita uma pré reserva dos ingressos, deixando-os indisponíveis até o usuário finalizar a compra. Cada compra terá um tempo máximo para finalização. Caso o usuário ultrapasse o tempo máximo, os ingressos ficaram disponíveis novamente e o usuário será notificado que o tempo foi execedido.

- A arquitetura do sistema está baseada em uma comunicação entre os serviços através de comandos (ações do usuário) e eventos (ações dos serviços).

Para maior detalhes da estrutura, é possível visualizar pelo link: [Miro](https://miro.com/app/board/uXjVP3YDaiE=/?share_link_id=701455484516)

<img width="1369" alt="image" src="https://github.com/lucianogomes02/festival-de-musica-design/assets/76966599/6e2664b6-d1ee-41c8-8cb9-4c010c0d2896">

