# Vote
Vote é um sistema aberto de votações. Sua função principal é permitir a ocorrência de processos de votação (ex.: eleições) de maneira descentralizada e imutável.
## A tese
A tese em que se baseia essa implementação é a de que provedores forneçam, através de uma API, dados que possam ser usados para criar o processo de eleição.

O fluxo das votações, no entanto, ocorre em um servidor aberto diferente daquele em posse do provedor, sendo garantidas todas as condições de sigilo dos dados e das votações.
## Provedor
Se entende como provedor o cliente que busca criar um processo eleitoral (ex.: governos, empresas). Os provedores devem possuir uma API capaz de fornecer os dados necessários para a ocorrência de uma votação.

O dados necessários:
- **Eleitores:** Deve haver um identificador único; Devem haver pelo menos 3 informações de cunho pessoal; Deve haver informações da região de votação;
- **Opções de voto:** Deve haver um identificador único numérico;
- **Questões:** Devem haver pelo menos 3 questões, cujas respostas são informações de cunho pessoal do usuário;

## Sistema de Votação
O sistema de votação ocorre em um servidor distindo daquele em posse do provedor. Seus dados são abertos, sendo possível consultas por qualquer cliente HTTP.

Garantias necessárias:
- Os dados de cunho pessoal do eleitor não podem ser persistidos;
- Deve ser impossível vizualizar o voto do eleitor através do sistema, durante ou depois da votação;

O funciamento do sistema ocorre em três etapas:
Validação | Autenticação | Votação
:-------- | :----------- | :------
O usuário deve possuir às condições estabelecidas durante a criação da eleição | O usuário deve responder adequandamente às questões | O usuário autenticado deve enviar as informações do voto
O usuário não pode ter um voto computado na eleição | Pode haver verificação facial, se houver foto | 

