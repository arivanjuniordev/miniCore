# miniCore

Arquitetura MiniCore

O principal objetivo dessa arquitetura é seu foco no FrontEnd. A estrutura é composta por três camadas distintas: User Interactor, Adaptation e External, proporcionando assim, um baixo acoplamento. Esse design visa aprimorar a experiência de desenvolvimento, promovendo eficiência e flexibilidade através da clara separação das responsabilidades em cada camada.

A camada User Interactor no miniCore assume a responsabilidade crucial de gerenciar a interação com o usuário. A camada Adaptation desempenha um papel fundamental ao adaptar informações provenientes da camada externa para a camada User Interactor. Já a camada External assume a responsabilidade de armazenar dados voláteis que estão sujeitos a constantes alterações.

Dentro dos limites arquiteturais estabelecidos, destaca-se que a camada User Interactor não possui acesso direto à camada External. Para contornar essa restrição, a camada Adaptation atua como intermediária, facilitando a comunicação entre a camada User Interactor e a camada External.



