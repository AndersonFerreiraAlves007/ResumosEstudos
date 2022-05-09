# Devops

## O que é Devops

Dev (desenvolvimento)
Ops (operação) - suport, sustentação e infraestrutura

Devops é cultura

Cultura é um modo de pensar, comportar-se ou trabalhar que existe em lugar ou organização

Defende fortemente a automação e automação de todas as fases da construção do software

Ciclos de desenvolvimento menores, frequencia de implantação aumentadas, liberações mais seguras.

Pontos Obrigatórios:
  - Colaboração entre as equipes (dev + ops)
  - Desenvolvimento ágil (versionamento, e validação da qualidade)
  - fornecer ciclos de entregas rápidas
  - integração comtínua e entrega contínua
  - testar (ferramentas de testes na integração comtinua)
  - gerência de configuração de software
  - centralizar logs
  - monitorar e coletar métricas
  - infraestrutura escalável
  - automatizar

# Porque devo adotar o Devops

Ciclos de desenvolvimento mais curtos, inovação mais rápida, vantagem em relação aos concorrentes

Diminuição de tarefas manuais

Riscos relativamente baixos, detecta problemas nos testese com métricas e monitoramento

Falhas e reversão, identifica rapidamente os erros

Melhorar comunicação e colaboração, maior confiabilidade, processo se torna cada vez mais continúo, euipes combinada , meta conjunta e não por área,

Maior eficiencia, o desenvolvedor se concentra em tarefas q não pode ser automatizada como a escrita de código e deixa por exemplo a execução dos testes para um ambinete automatizado

Custos reduzidos e Headcount de TI, ganho não será vistos imediatamente, redistribuir o time em tarefas relacionadas ao negocio e não em tarefas manuais

# Timeline

2001 - Manifesto Ágil

2003 - Google SRE - disponibilidade, latencia, toda operação

2009 - aprensenta a metadologia do Devops

2012 - primeiras ferramentas de Devops

2013 - pesquisas sobre devops e principais tendências

# Conceitos

Desenvolvedores querem:

- mudança contínua
- adicionar novos recursos

Equipe de operação quer:

- Estabilidade contínua 
- criar novos serviços

Bussines da empresa e o cliente sempre é o foco principal

# CAMS

Cultura da empatia, anos 90, inicioa 2000

Pilares do devops

C - Cultura, pessoas e processos primeiro, relacionamentos
A - Automação, aspecto mais visivel do devops, 
M - Medição, se não pode medir não pode melhorar, medir tudo q for possivel
S - Compartilhamento, precisa sempre compartilhar idéias e problemas

Relacionmaneo:

- Envolva-se cedo, envolva-se com frequência
- Destruir silos, barreiras
- Esteja aberto a aopções
- Pare de culpra
- comuniqui-se
- envolva todos
- pergunte
- nunca diga nunca
- reunioes diarias e curtas

Automação:

- diminui custos, o que aumenta a os lucros
- evita defeitos
- consistencia no software
- focar na qualidade
- não despediçar tempo com tarefas manuais
- prensent em: gerenciamento de versões, gerenciamento de configuração, integração de sistemas, monitoramento, orquestração, builds, implantações, testes, verificação de qualidade, 

Medição:

- métricas de desempenho
- metricas de processo
- metricas de pessoas

Os dados vem ser:

- Transparentes
- Acessíveis
- significativos
- Visualizados para um fim especifico

Compartilhar

- senso de engajamento
- Eliminar trabalho duplicado

Deve-se compartilhar:

- Idéias
- Métricas
- Resultados
- Sucessos
- Falhas, não ter vergolha de expor as falhas, pode ajudar outros times a não repetir o erro

Fail Wall, parade do que falhou de fácil visualização

# PPT

P - Pessoas
P - Processos
T - Tecnologia

Em essencia o Devops é a eficiencia colocada nessas 3 areas

Pessoas:

- Pessoas q se comunicam entre si, colaborando e mudando mentalidade, para ver objetivos conjuntos
- Devops não é apenas sobre desenvolvedores e operações, sobre todas as pessoas q colaboram e como elas colaboram
- Derrubar barreiras, quebrar estrutura hierarquica, todos podem expressar idéias
- Novos papéis, novos titulos e novas responsabilidades
- foco no negócio e não na tecnologia, confiança nas pessoas e nas tecnologias
- Capacitação das pessoas, novas habilidades tecnologicas, atualizar conhecimento ou mais colaboradores, equilíbrio
- Exige colaboração e cooperação

Processo:

- requer mudanças nos processos
- colaboração entre desenvolvimento e operação
- melhorar e automatizar processor
- remover restrições
- melhorar fluxo de código para entrega
- criar loops de feedback em todas as fases

Tecnologias:

- Ferramentas
- Colaboração
- Construção
- Qualidade
- Implantação
- Produção

# Ferramentas

Ferramentas não são Devops, o que torna uma ferramentas Devops, é a maneira de usá-las

Colaboração:

- Trello
- Jira
- Microsoft Teams
- Documentação
- Compartilhamento de conhecimento
- Gerenciamento de projeto
- ALM

Construção:

- Versionamento de código, github
- Integração contínua, jenkins, azure devops
- Build
- Gerenciamento de banco de dados

Qualidade:

- Teste de unidade
- BDD/TDD
- Teste de segurança
- Teste de integração
- Testes Automatizados

Implantação:
- Ferramentas de implantação
- Confi/Provisionamento
- Gerenciamento de arqtefatos, npm, docker

Produção:

- nuvem
- IAAS
- PAAS
- Orquestração e Agendamento
- Monitoramento e logging

# Devops Ágil:

- Dsenvolvimento ágil (código e build)
- Integração contínua (codigo, build, integração e testes)
- Entrega contínua (codigo, build, integração ,testes e release)
- Implantação contínua (codigo, build, integração ,testes ,release e deploy)
- Devops (codigo, build, integração ,testes ,release ,deploy, operação)