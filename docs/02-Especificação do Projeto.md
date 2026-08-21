
# Especificações do Projeto

**Versão:** 1.0 · **Data:** 10 de agosto de 2026 · **Status:** proposta para validação

<span style="color:red">Pré-requisitos: <a href="1-Documentação de Contexto.md"> Documentação de Contexto</a></span>

A TeamUp é uma plataforma web e mobile para jogadores de PC maiores de 18 anos encontrarem pessoas compatíveis para jogar. O produto substitui a busca fragmentada em Discord, redes sociais e chats de jogos por perfis estruturados, recomendações de compatibilidade, match mútuo, chat e organização de partidas.

### Problema sob a perspectiva do usuário

“Quero encontrar rapidamente pessoas confiáveis para jogar comigo, que usem a mesma plataforma, tenham disponibilidade e objetivos parecidos com os meus, sem ter que procurar em vários grupos desorganizados e confusos.”

### Proposta de solução

A pessoa cria um perfil com jogos, elo, estilo, objetivos e horários. A TeamUp calcula e apresenta candidatos compatíveis; quando há interesse mútuo, cria um match e libera a conversa. A pessoa também pode publicar e entrar em partidas agendadas.

### Escopo do MVP

A TeamUp terá como MVP uma plataforma para conectar jogadores que procuram pessoas compatíveis para jogar, considerando informações como jogos de interesse, elo, estilo de jogo, objetivos e disponibilidade.

O foco inicial da aplicação será o **Match, comunicação e Jogue Agora**, permitindo que o usuário encontre jogadores com interesses semelhantes, realize Match, converse e encontre pessoas disponíveis para jogar naquele momento.

### Arquitetura da Solução

A TeamUp será desenvolvida como uma **aplicação distribuída**, composta por uma aplicação Web, uma aplicação Mobile, um backend centralizado e um banco de dados NoSQL.

As versões Web e Mobile utilizarão o mesmo backend e os mesmos dados, porém terão interfaces adaptadas às características de cada plataforma.

- **Web:** maior foco no recurso **Jogue Agora**, busca e interação com jogadores disponíveis.
- **Mobile:** maior foco em **Match, interação social e comunicação**.
- **Backend:** responsável pelas regras de negócio, autenticação, usuários, Match, chat, jogos, avaliações, disponibilidade e demais funcionalidades.
- **Banco de dados:** responsável pelo armazenamento dos dados da aplicação.

A comunicação entre Web, Mobile e Backend será realizada por meio de uma **API REST**, utilizando

## Personas

| Persona | Tipo | Contexto e necessidade | Principal dor |
|---|---|---|---|
| **Lucas, 23 anos** | Competitivo | Joga Valorant no PC à noite e busca uma dupla com elo e objetivos semelhantes para subir de ranking. | Perde tempo em servidores com pedidos irrelevantes. |
| **Marina, 27 anos** | Social/Casual | Joga cooperativos nos fins de semana e procura pessoas respeitosas para partidas leves e descontraídas. | Não consegue avaliar afinidade e segurança antes de jogar. |
| **Rafael, 31 anos** | Organizador | Reúne amigos para jogos em equipe e precisa completar vagas para partidas marcadas. | Confirmações e desistências ficam dispersas em diferentes chats. |
| **Ana, 29 anos** | Moderadora | Administra a segurança da plataforma, analisando denúncias e garantindo o cumprimento das regras. | Precisa avaliar denúncias e aplicar medidas de forma organizada e rastreável. |
## Histórias de Usuários

Com base na análise das personas forma identificadas as seguintes histórias de usuários:

|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE` |PARA ... `MOTIVO/VALOR`                 |
|--------------------|------------------------------------|----------------------------------------|
| Lucas — Jogador competitivo | Criar minha conta e informar meus jogos, elo, estilo de jogo e disponibilidade. | Encontrar jogadores compatíveis com meu perfil. |
| Lucas — Jogador competitivo | Receber recomendações de jogadores com jogos e elo semelhantes aos meus. | Encontrar parceiros adequados para jogar. |
| Lucas — Jogador competitivo | Curtir ou recusar jogadores recomendados. | Criar um Match quando houver interesse mútuo. |
| Lucas — Jogador competitivo | Encontrar jogadores disponíveis para jogar naquele momento. | Formar uma partida sem depender de um lobby aleatório. |
| Lucas — Jogador competitivo | Avaliar jogadores após uma partida. | Contribuir com a reputação dos jogadores dentro da plataforma. |
| Marina — Jogadora social/casual | Informar meus jogos favoritos, estilo de jogo e objetivos. | Encontrar pessoas com interesses semelhantes aos meus. |
| Marina — Jogadora social/casual | Encontrar jogadores com interesses e estilos semelhantes aos meus. | Criar novas amizades através dos jogos. |
| Marina — Jogadora social/casual | Conversar com jogadores com quem tive Match. | Conhecer melhor a pessoa e combinar a partida. |
| Marina — Jogadora social/casual | Bloquear ou denunciar jogadores. | Evitar interações inadequadas e ter mais segurança na plataforma. |
| Marina — Jogadora social/casual | Avaliar jogos e escrever comentários. | Compartilhar minha experiência com outros jogadores. |
| Rafael — Organizador | Informar jogo, elo, objetivo e horário em que estou disponível. | Encontrar jogadores interessados em participar da partida. |
| Rafael — Organizador | Encontrar jogadores compatíveis para minha partida. | Completar minha equipe. |
| Rafael — Organizador | Conversar com os jogadores interessados. | Combinar os detalhes da partida. |
| Rafael — Organizador | Receber notificações sobre Matches, mensagens e interações. | Acompanhar as atividades relacionadas às minhas partidas. |
| Ana — Moderadora | Visualizar e analisar denúncias realizadas pelos usuários. | Identificar comportamentos inadequados na plataforma. |
| Ana — Moderadora | Bloquear ou banir usuários que violem as regras da plataforma. | Manter a comunidade segura. |
| Ana — Moderadora | Analisar solicitações de reavaliação de usuários banidos. | Decidir pela manutenção ou remoção da penalidade. |
| Ana — Administradora | Cadastrar, editar e remover jogos da biblioteca. | Manter os jogos disponíveis na plataforma atualizados. |


## Modelagem do Processo de Negócio 

### Análise da Situação Atual

Apresente aqui os problemas existentes que viabilizam sua proposta. Apresente o modelo do sistema como ele funciona hoje. Caso sua proposta seja inovadora e não existam processos claramente definidos, apresente como as tarefas que o seu sistema pretende implementar são executadas atualmente, mesmo que não se utilize tecnologia computacional. 

### Descrição Geral da Proposta

Apresente aqui uma descrição da sua proposta abordando seus limites e suas ligações com as estratégias e objetivos do negócio. Apresente aqui as oportunidades de melhorias.

### BPMN 1 – Processo atual sem App

<img width="647" height="512" alt="BPMN 1 - Processo atual sem App" src="https://github.com/user-attachments/assets/5354fa22-29a2-49a6-b8fb-42821d7c2bc8" />


### BPMN 2 – Com o app FairPlay

<img width="642" height="570" alt="BPMN 2 – Com o app FairPlay" src="https://github.com/user-attachments/assets/5e77041d-3eb9-43fd-bb1c-814c169e98ad" />


## Indicadores de Desempenho


 ### Dashboard

<img width="1104" height="657" alt="Image" src="https://github.com/user-attachments/assets/23ed94b7-5b75-43b6-a44b-41f0f6ed86c5" />

### Gráficos

<img width="744" height="714" alt="Image" src="https://github.com/user-attachments/assets/013a7c83-a2ff-430b-b3f8-665ab691e521" />

Feitos no Excel:
https://sgapucminasbr-my.sharepoint.com/personal/1596849_sga_pucminas_br/_layouts/15/guestaccess.aspx?share=IQAtNptNGlgyT5L_BnQhaW7zAawQZr3OI8-bM31bxzRV9pA&e=MsYFPC 

## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

| ID | Descrição do Requisito | Prioridade |
|---|---|---|
| RF-001 | O sistema deve permitir que o usuário crie uma conta informando seus dados pessoais, credenciais e confirmação de maioridade. | ALTA |
| RF-002 | O sistema deve permitir que o usuário informe e altere seus jogos, plataforma, elo, estilo de jogo, objetivos e disponibilidade. | ALTA |
| RF-003 | O sistema deve apresentar jogadores compatíveis considerando jogos de interesse, elo, estilo de jogo, objetivos e disponibilidade. | ALTA |
| RF-004 | O sistema deve permitir que o usuário curta ou recuse jogadores recomendados, gerando um Match quando houver interesse mútuo. | ALTA |
| RF-005 | O sistema deve permitir que usuários com Match troquem mensagens privadas. | ALTA |
| RF-006 | O sistema deve permitir que o usuário bloqueie ou denuncie outros jogadores, interrompendo a interação quando necessário e encaminhando a denúncia para análise. | ALTA |
| RF-007 | O sistema deve permitir que o usuário encontre jogadores disponíveis para jogar naquele momento, utilizando critérios como jogo, elo e objetivo da partida. | ALTA |
| RF-008 | O sistema deve permitir que o usuário informe jogo, elo, objetivo e disponibilidade para aparecer na seção "Jogue Agora" e ser encontrado por outros jogadores. | ALTA |
| RF-009 | O sistema deve permitir que os usuários consultem uma biblioteca de jogos cadastrados na plataforma, visualizando informações como nome, imagem, gênero, plataforma e sinopse. | MÉDIA |
| RF-010 | O sistema deve permitir que os usuários avaliem os jogos cadastrados utilizando uma escala de estrelas e, opcionalmente, publiquem comentários sobre o jogo. | MÉDIA |
| RF-011 | O sistema deve permitir que os usuários avaliem jogadores após uma interação ou partida, contribuindo para sua reputação dentro da plataforma. | MÉDIA |
| RF-012 | O sistema deve notificar o usuário sobre eventos relevantes, como novos Matches, mensagens, avaliações e outras interações realizadas na plataforma. | MÉDIA |
| RF-013 | O sistema deve permitir que o usuário visualize o perfil público de outros jogadores, incluindo jogos, elo, estilo de jogo, avaliações e disponibilidade, respeitando as configurações de privacidade. | MÉDIA |
| RF-014 | O sistema deve permitir que o administrador visualize denúncias, analise ocorrências e aplique medidas administrativas, incluindo bloqueio ou banimento de usuários. | ALTA |
| RF-015 | O sistema deve permitir que um usuário banido solicite a reavaliação da penalidade, possibilitando ao administrador analisar e decidir pela manutenção ou remoção do banimento. | MÉDIA |
| RF-016 | O sistema deve permitir que o administrador cadastre, edite e remova jogos da biblioteca da plataforma, incluindo informações como nome, imagem, gênero, plataforma e sinopse. | MÉDIA |
| RF-017 | O sistema deve permitir que o administrador cadastre, edite, ative, desative e exclua anúncios relacionados ao universo gamer exibidos na plataforma. | BAIXA |


### Requisitos não Funcionais

| ID | Descrição do Requisito | Prioridade |
|---|---|---|
| RNF-001 | As principais operações da aplicação devem responder em até 3 segundos em condições normais de utilização, incluindo busca de jogadores, carregamento de perfis, envio de mensagens e consulta de partidas disponíveis. | ALTA |
| RNF-002 | As senhas dos usuários devem ser armazenadas utilizando mecanismo seguro de hash e salt, não sendo armazenadas em texto puro. | ALTA |
| RNF-003 | A aplicação deve permanecer disponível durante manutenções ou atualizações de componentes individuais, evitando que a indisponibilidade de um serviço interrompa o funcionamento dos demais. | ALTA |
| RNF-004 | A aplicação deve disponibilizar as mesmas funcionalidades principais nas versões Web e Mobile, adaptando a interface, navegação e disposição dos elementos às características de cada plataforma. | ALTA |
| RNF-005 | A arquitetura da aplicação deve permitir a expansão da quantidade de usuários, partidas, Matches, mensagens e jogos cadastrados sem exigir alterações significativas na estrutura dos serviços existentes. | MÉDIA |
| RNF-006 | Um usuário deve conseguir realizar as principais ações da aplicação, como encontrar jogadores, realizar um Match, iniciar uma conversa e procurar jogadores no Jogue Agora, sem necessidade de treinamento prévio. | ALTA |
| RNF-007 | A aplicação deve impedir a criação de registros duplicados ou conflitantes que comprometam a integridade dos dados, especialmente em contas, Matches, avaliações e disponibilidade de jogadores. | ALTA |
| RNF-008 | As mensagens enviadas pelo chat devem ser entregues ao destinatário sem duplicidade e manter a identificação do remetente, destinatário e data/hora do envio. | ALTA |
| RNF-009 | O sistema deve garantir que um Match seja criado somente quando houver interesse mútuo entre os jogadores e que cada combinação de jogadores resulte em no máximo um Match ativo. | ALTA |
| RNF-010 | As informações de disponibilidade dos jogadores devem refletir seu estado atual, removendo ou atualizando automaticamente uma disponibilidade que tenha expirado ou sido encerrada pelo usuário. | ALTA |
| RNF-011 | Os dados essenciais da conta, perfil, Matches, mensagens, avaliações e disponibilidade devem permanecer sincronizados entre as versões Web e Mobile da aplicação. | ALTA |
| RNF-012 | A aplicação deve possuir arquitetura modular, separando responsabilidades entre seus componentes e serviços, permitindo manutenção ou atualização de um componente sem exigir alterações nos demais quando não houver dependência direta. | MÉDIA | 


## Restrições

| ID | Descrição da Restrição |
|---|---|
| R01 | O backend da aplicação deverá ser desenvolvido utilizando C# e ASP.NET Core Web API. |
| R02 | A aplicação Web deverá ser desenvolvida utilizando React e JavaScript. |
| R03 | A aplicação Mobile deverá ser desenvolvida utilizando React Native. |
| R04 | O sistema deverá utilizar MongoDB como banco de dados não relacional (NoSQL). |
| R05 | A comunicação entre as aplicações Web, Mobile e o backend deverá ocorrer por meio de uma API REST, utilizando requisições HTTP e dados no formato JSON. |
| R06 | O sistema deverá possuir versões Web e Mobile, compartilhando o mesmo backend e banco de dados, com funcionalidades equivalentes e interfaces adaptadas às características de cada plataforma. |
| R07 | O desenvolvimento deverá utilizar Git e GitHub para controle de versão e integração do trabalho entre os integrantes da equipe. |
| R08 | O desenvolvimento deverá utilizar Visual Studio para o backend e Visual Studio Code para as aplicações Web e Mobile. |
| R09 | A aplicação deverá ser disponibilizada em ambiente de hospedagem compatível com sua arquitetura, utilizando Azure, SmartASP.NET ou outro serviço definido pela equipe e aprovado para o projeto. |
| R10 | As versões Web e Mobile deverão consumir a mesma API e compartilhar os dados armazenados no MongoDB, não sendo permitido o acesso direto ao banco de dados pelos aplicativos clientes. |


## Diagrama de Casos de Uso

<img width="1344" height="1142" alt="Diagrama de Caso de Uso FairPlay" src="https://github.com/user-attachments/assets/05a1b13e-f309-4e6f-aa59-f3bd29601043" />

> **Links Úteis**:
> - [Criando Casos de Uso]([https://www.ibm.com/docs/pt-br/elm/6.0?topic=requirements-creating-use-cases](https://lucid.app/lucidchart/b3bc78c2-3ccd-455d-91ed-86c4f5b0aabc/edit?invitationId=inv_8253ba6e-fafb-4b5d-89f0-8a01d9dee1ac&page=0_0#)


# Matriz de Rastreabilidade

Cruzado entre Product Owner, Product Manager, Requisitos Funcionais e Requisitos Não Funcionais.

teste

<img width="1033" height="545" alt="Image" src="https://github.com/user-attachments/assets/e7f577c8-8aa9-45c8-973e-d63723594670" />

<img width="2480" height="1026" alt="Matriz Rastreabilidade" src="https://github.com/user-attachments/assets/c56af57f-fd14-4ed9-9056-02736f46adc1" />

> **Links Úteis**:
> - [Matriz - Rastreabilidade](https://docs.google.com/spreadsheets/d/1C4A2cVXVXwLHyOIN7LM2g5ma48oLScUoOhXD7nikhKQ/edit?gid=0#gid=0)


# Gerenciamento de Projeto

De acordo com o PMBoK v6 as dez áreas que constituem os pilares para gerenciar projetos, e que caracterizam a multidisciplinaridade envolvida, são: Integração, Escopo, Cronograma (Tempo), Custos, Qualidade, Recursos, Comunicações, Riscos, Aquisições, Partes Interessadas. Para desenvolver projetos um profissional deve se preocupar em gerenciar todas essas dez áreas. Elas se complementam e se relacionam, de tal forma que não se deve apenas examinar uma área de forma estanque. É preciso considerar, por exemplo, que as áreas de Escopo, Cronograma e Custos estão muito relacionadas. Assim, se eu amplio o escopo de um projeto eu posso afetar seu cronograma e seus custos.

## Gerenciamento de Tempo

Com diagramas bem organizados que permitem gerenciar o tempo nos projetos, o gerente de projetos agenda e coordena tarefas dentro de um projeto para estimar o tempo necessário de conclusão.

<img width="1867" height="320" alt="Image" src="https://github.com/user-attachments/assets/cd4b1af5-3321-406f-a559-a27b6b4531ea" />

O gráfico de Gantt ou diagrama de Gantt também é uma ferramenta visual utilizada para controlar e gerenciar o cronograma de atividades de um projeto. Com ele, é possível listar tudo que precisa ser feito para colocar o projeto em prática, dividir em atividades e estimar o tempo necessário para executá-las.

<img width="1682" height="144" alt="Image" src="https://github.com/user-attachments/assets/291ebf6e-872f-4d23-91af-cc9e83bcfc17" />

## Gerenciamento de Equipe

# Cronograma do Projeto

O desenvolvimento do FairPlay está organizado em cinco fases evolutivas, seguindo uma abordagem incremental, com entregas progressivas até a consolidação da versão final do produto.

---

## Fase 1 – Definição Estratégica e Planejamento  
**Período:** 09/02/2026 a 08/03/2026  

### Entregas:
- Documento de Contexto do Produto  
- Especificação do Problema  

**Objetivo:**  
Definir o posicionamento do FairPlay, identificar o problema central a ser resolvido e estabelecer as bases estratégicas do projeto.

---

## Fase 2 – Estruturação da Solução  
**Período:** 09/03/2026 a 05/04/2026  

### Entregas:
- Definição da metodologia de desenvolvimento  
- Arquitetura da solução  
- Projeto de interface (UI)  
- Implementação inicial das funcionalidades principais  
- Definição de indicadores de desempenho  

**Objetivo:**  
Estruturar tecnicamente o sistema e iniciar a construção da primeira versão funcional.

---

## Fase 3 – Expansão e Validação  
**Período:** 06/04/2026 a 10/05/2026  

### Entregas:
- Evolução das funcionalidades  
- Plano de testes funcionais  
- Plano de testes de usabilidade  
- Registro e análise dos testes realizados  

**Objetivo:**  
Ampliar as funcionalidades do FairPlay e validar seu desempenho e experiência de uso.

---

## Fase 4 – Consolidação e Estabilização  
**Período:** 11/05/2026 a 31/05/2026  

### Entregas:
- Refinamento das funcionalidades  
- Correções e melhorias  
- Atualização dos registros de testes  
- Preparação da versão estável do sistema  

**Objetivo:**  
Garantir qualidade, estabilidade e consistência antes da entrega final.

---

## Fase 5 – Finalização e Apresentação  
**Período:** 01/06/2026 a 21/06/2026  

### Entregas:
- Consolidação da versão final  
- Documentação final  
- Apresentação oficial do projeto  

**Objetivo:**  
Formalizar a conclusão do desenvolvimento do FairPlay e apresentar os resultados obtidos.


## Gestão de Orçamento

O processo de determinar o orçamento do projeto é uma tarefa que depende, além dos produtos (saídas) dos processos anteriores do gerenciamento de custos, também de produtos oferecidos por outros processos de gerenciamento, como o escopo e o tempo.

<img width="936" height="354" alt="Image" src="https://github.com/user-attachments/assets/e708ae2f-0043-4ee7-9650-4468c34b9c8f" />



