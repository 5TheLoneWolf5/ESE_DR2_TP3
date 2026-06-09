# Projeto Pet Friends





### Lista de Bounded Contexts



* Ponto de Venda;
* Agendamento;
* Veterinários;
* Passeadores;
* Tosadores;
* Conselho Federal de Medicina Veterinária;
* Produtos;
* Matriz;
* Entrega;
* Assinatura. 



### Mapa de Contexto (com relacionamentos)



<img width="1261" height="1021" alt="pet_friends_context_map" src="https://github.com/user-attachments/assets/1c9d0831-2e8c-4405-aee2-a3973a17af38" />


### Versão 2 (melhorada):



<img width="822" height="818" alt="pet_friends_context_map_v2" src="https://github.com/user-attachments/assets/81a2e937-0b94-4d24-b7b8-14a7372f113b" />


### Classificação de Subdomínios (e justificativas)



* Lojas -> Support.
* Registro -> Generic.
* Remédio -> Core.
* Diversão -> Core.
* Higiene -> Core.
* Pacote -> Core.
* Correio -> Generic.

Arguição: os subdomínios core fazem parte do modelo de negócio principal de Pet Friends, e estão conectados aos contextos de produtos e agendamentos (o que a empresa oferece de diferencial). As lojas físicas são essenciais para a operação, mas não são o diferencial, portanto são suporte para os core. Os subdomínios de Lojas e Correios são genéricos, por fazerem parte de contextos externos dentro do domínio. 


### Lista de Estratégias envolvendo o contexto de Veterinário



O contexto de veterinários possui múltiplas relações. São elas os relacionamentos com os contextos: Produtos, Agendamento e Conselho Federal de Medicina Veterinária. Ele possui um shared kernel com produtos, por meio do subdomínio de Remédio. Com Agendamento, Veterinários tem uma relação de Customer-Supplier, sendo o Veterinário (assim como os outros colaboradores) o Customer. Veterinários também se comunica com o Conselho Federal de Medicina Veterinária, responsável pela credenciamento dos mesmos. Para obter as informações desse contexto externo da organização, os dados são tratados por meio de um ACL, que então se comunica com o contexto de Veterinários.

