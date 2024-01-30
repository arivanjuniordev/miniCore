# miniCore

Arquitetura MiniCore

O principal objetivo dessa arquitetura é seu foco no FrontEnd. A estrutura é composta por três camadas distintas: User Interactor, Adaptation e External, proporcionando assim, um baixo acoplamento. Esse design visa aprimorar a experiência de desenvolvimento, promovendo eficiência e flexibilidade através da clara separação das responsabilidades em cada camada.

A camada User Interactor no miniCore assume a responsabilidade crucial de gerenciar a interação com o usuário. A camada Adaptation desempenha um papel fundamental ao adaptar informações provenientes da camada externa para a camada User Interactor. Já a camada External assume a responsabilidade de armazenar dados voláteis que estão sujeitos a constantes alterações.

Dentro dos limites arquiteturais estabelecidos, destaca-se que a camada User Interactor não possui acesso direto à camada External. Para contornar essa restrição, a camada Adaptation atua como intermediária, facilitando a comunicação entre a camada User Interactor e a camada External.

<img src="image.png" width="512" alt="Achitecture diagram"/>

A camada User Interaction é o espaço designado para a gestão de estados e ações do usuário. Nela, definiremos e controlaremos as interações do usuário durante o uso do sistema.

Por outro lado, a camada Adaptation desempenhará um papel crucial, conectando-se a interfaces com APIs e bancos de dados. Essa camada é responsável por facilitar a comunicação e a adaptação eficiente de dados entre o sistema e fontes externas, garantindo uma integração suave e eficaz e a nossa camada External como falado anteriormente assume a responsabilidade de armazenar dados voláteis que estão sujeitos a constantes alterações.

## Estruturando nossa Arquitetura

### External
fica responsável por declarar as entradas, saídas e interações da aplicação.
Usando o Flutter como exemplo, usariamos os Widgets, Pages e subpages.

### User Interaction
Onde encontramos nossos estados, reatividades e ações(onde usaremos funções puras para modificar nossos estados ou reatividades).

### Adaptation
Onde encontramos nossas adaptações, como serialização e nossa comunicação com apis e banco de dados locais.

## Proposta de estrutura de pasta e pattern para utilização da arquiterura

As estrutura de pastas deve ficar como no exemplo abaixo.

```
.
└── app/
    ├── public/
    │   └── pages
    ├── core/
    │   ├── assets
    │   ├── themes
    │   └── widgets
    ├── data/
    │   ├── repositories
    │   └── services
    └── interactor/
        ├── atoms
        ├── actions
        ├── dtos
        ├── models 
        ├── repositories
        └── services
```

## Public
Na camada Public, encontram-se as páginas e subpáginas do aplicativo, sendo responsável pela apresentação visual e interativa.

## Interactor
Na camada Interactor, assume-se a responsabilidade pela execução das regras de negócios. Nela estão presentes patters como como ASP - Atomic State Pattern, DTO(Data Transfer Object), Models, Prototype e para o baixo acomplamentos colocamos os contratos do repositório e dos serviços.

- #### Atoms: 
    Atom refere-se a um estado que possui reatividade própria, contribuindo para a dinâmica do objeto.

- #### Actions: 
    Actions têm o propósito de ser funções puras para modificar nossos estados ou reatividades.

- #### DTO: 
    O Data Transfer Object é um padrão de design usado para transferir dados entre camadas, assegurando uma comunicação eficiente.

- #### Models: 
    Models representa a estrutura de dados e as regras de negócios da aplicação.

- #### Prototype:
    É um padrão de design creacional que visa criar novos objetos duplicando, ou clonando, objetos existentes

- #### Contratos: 
    Nessa seção incluímos interfaces do repositório e serviços, delineando claramente os compromissos necessários.

## Data
A camada Data assume a responsabilidade de interagir tanto com fontes externas (APIs) quanto internas (Banco de dados locais).

- #### Adapter:
    Define que precisa ser adaptada.

- #### Repository: 
    O padrão Repository proporciona uma abstração entre a lógica de negócios e o acesso aos dados, simplificando a gestão e manipulação desses dados.

- #### Service: 
    O padrão Service, amplamente utilizado em arquiteturas de software, encapsula a lógica de negócios para promover modularidade, reutilização e facilidade de manutenção.

## Core
Na camada Core, encontram-se dados globais e reutilizáveis fornecidos para todas as camadas da aplicação, incluindo como exemplo: temas, widgets, design system e dados compartilhados. Essa camada é fundamental para manter a coesão e consistência em toda a aplicação.







