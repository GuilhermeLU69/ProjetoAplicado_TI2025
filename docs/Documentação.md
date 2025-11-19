# 1. Equipe e Planejamento
## 1.1 Integrantes e funções

 ─────────────────────────────────────────────────────────────────────────────────────┐
 │                              INTEGRANTES E FUNÇÕES                                 │
 ├────────────────────────────────────────────────────────────────────────────────────┤
 │ Nataliny Eleutério da Silva │  Analista de Requisitos │ Responsável por requisitos │
 ├────────────────────────────────────────────────────────────────────────────────────┤
 │  Henrique Hermes            │  Prototipagem           │ Suporte Técnico            │
 ├────────────────────────────────────────────────────────────────────────────────────┤
 │  José Lissandro dos Santos  │  Back-End               │ Testes Funcionais          │
 ├────────────────────────────────────────────────────────────────────────────────────┤
 │  Guilherme Thiago Gellert   │  Lógica                 │ Front-End                  │
 └────────────────────────────────────────────────────────────────────────────────────┘

# 2. Problema e Descrição

## 2.1 Descrição do problema

Em nosso cenário, a empresa enfrenta dificuldades na área de Tecnologia da 
Informação decorrentes da falta de organização e controle dos chamados técnicos de T.I. 
Diante de tal cenário, torna-se essencial implementar uma solução integrada que traga 
organização, controle e inteligência à área de T.I. A nossa proposta será uma aplicação 
chamada “TIcket Express” e deve ir além da simples correção pontual: ela precisa transformar 
os processos, garantir rastreabilidade dos ativos, e fornecer dados confiáveis para decisões 
estratégicas. 

## 2.2 Impacto

A falta de um sistema integrado compromete a eficiência da equipe e compromete a 
qualidade do serviço desenvolvido por diversos setores da empresa. Dentre as possíveis 
consequências da problemática, podemos citar: 
- Atrasos na resolução de problemas. 
- Retrabalho constante. 
- Decisões baseadas em achismos. 
- Dificuldade em identificar gargalos. 
- Baixa previsibilidade. 
- Aumento de custos operacionais. 
- Perda de produtividade. 
- Tempo de inatividade prolongado. 
- Insatisfação dos colaboradores. 
- Frustração dos usuários e insatisfação com os serviços de T.I. 
- Imagem negativa da área de T.I. 
- Falta de confiança nos processos internos.

## 2.3 Justicativa

A ausência de um sistema integrado para organização de chamados técnicos e gestão 
de ativos de T.I. na empresa tem gerado atrasos, falhas recorrentes e falta de indicadores 
confiáveis para tomada de decisão. O desenvolvimento deste sistema permitirá padronizar 
registros, garantir rastreabilidade, melhorar a comunicação entre usuários e técnicos e 
fornecer relatórios precisos para otimizar processos, aumentar a produtividade e reduzir 
impactos operacionais, utilizando tecnologias acessíveis e de baixo custo. 
- Atrasos na resolução de problemas: Quando o suporte técnico demora a atender, as 
atividades do dia a dia ficam travadas, o que atrasa entregas e compromete o 
rendimento dos colaboradores. Mesmo tarefas rotineiras acabam levando mais 
tempo do que deveriam, processos que deveriam ser rápidos se tornam lentos e 
complicados, criando obstáculos no dia a dia, reduzindo a eficiência operacional como 
um todo e criando obstáculos no andamento dos processos e diminuindo a agilidade 
da empresa como um todo. 
- Retrabalho constante: A falta de registros e padronização leva à repetição de 
diagnósticos e soluções. As equipes não conseguem acessar informações em tempo 
real e isso os leva a perder tempo refazendo etapas que poderiam ser evitadas, o que 
gera retrabalho, sobrecarrega o suporte e compromete a agilidade na resolução dos 
problemas. 
- Decisões baseadas em achismos: A ausência de uma aplicação que gere relatórios 
adequados,faz com que os gestores não tenham indicadores confiáveis de dados 
concretos para agir. 
- Dificuldade em identificar gargalos: Sem métricas, não é possível saber onde estão os 
maiores problemas ou ineficiências.
Baixa previsibilidade: A ausência de registros estruturados impede análises preditivas 
e planejamento estratégico. 
- Aumento de custos operacionais: Equipamentos mal gerenciados geram gastos 
extras com manutenção corretiva ou substituição. 
- Perda de produtividade: Tempo perdido com falhas e chamados mal gerenciados 
impacta diretamente na eficiência dos colaboradores, pois a frustração os faz se 
sentirem que a tecnologia não os ajuda, mas atrapalha. 
- Tempo de inatividade prolongado: Cada minuto de paralisação pode ter um impacto 
significativo nos resultados financeiros da empresa, o desperdício de recursos, devido 
a falta de controle dos equipamentos, que podem ser comprados em duplicidade ou 
ficar ociosos devido a falhas técnicas e à repetidas necessidades de manutenção, 
geram interrupções frequentes e pode gerar receita extra. 
- Insatisfação dos colaboradores: Problemas recorrentes de T.I. geram frustração e 
desmotivação. 
- Frustração dos usuários e insatisfação com os serviços de T.I: Quando os 
colaboradores passam por dificuldades técnicas que os impede de fornecer um 
atendimento rápido e eficiente aos clientes, o sentimento de frustração cresce. Essa 
insatisfação compromete a imagem da equipe de T.I., gerando desconfiança sobre sua 
capacidade de resolver problemas e, em alguns casos, levando os usuários a procurar 
alternativas fora da empresa para suprir suas necessidades. 
- Imagem negativa da área de T.I.: A percepção de desorganização pode comprometer 
a credibilidade da empresa. 
- Falta de confiança nos processos internos: A ausência de controle e transparência 
mina a confiança na gestão.

# 3. Necessidades e Validação

## 3.1 Perfil do usuário

Funcionário: Abre o chamado, descreve o problema e acompanha a situação até 
solucionar o problema.
- Técnicos de Suporte: Recebe e registra chamados, organiza a fila, define prioridade e 
urgência, resolve casos simples, atualiza o status e comunica o andamento ao 
funcionário. 
- Especialista de TI: Assume chamados complexos, faz diagnóstico aprofundado (rede, 
sistemas, servidores), consulta o histórico do usuário e do equipamento, executa 
correções ou mudanças planejadas e registra a causa e a solução para evitar 
recorrências. 
- Gestor de TI: Acompanha volumes e prazos, define e revisa prazos (SLA), analisa 
indicadores, prioriza demandas, decide sobre recursos e melhorias e utiliza painéis e 
relatórios para orientar a equipe. 
- Responsável por Equipamentos e Licenças (inventário): cadastra e identifica cada 
ativo (etiqueta e ID), registra entradas, saídas e localização, controla garantias e 
renovações de licenças, vincula equipamentos aos chamados e gera relatórios de 
inventário e auditoria. 

## 3.2 Necessidades

- Necessidade 1: Centralizar e Padronizar a Abertura de Chamados. 
-- Descrição: Os usuários (tanto funcionários quanto a equipe de T.I.) precisam 
de um canal único para registrar todos os pedidos de suporte. Deve existir um 
formulário padrão, intuitivo e de fácil preenchimento, com possibilidade de 
anexar prints, documentos ou logs para melhor detalhamento. 

- Necessidade 2: Acompanhar o Andamento dos Chamados em Tempo Real. 
-- Descrição: Os usuários (funcionários) e a equipe de T.I. precisam de visibilidade 
contínua e atualizada sobre o status de seus chamados. Isso inclui um painel 
dedicado para acompanhamento e a implementação de alertas automáticos 
(via e-mail ou notificação no sistema) a cada mudança de status ou atualização 
relevante. A transparência no processo visa reduzir a ansiedade do usuário e 
evitar interrupções desnecessárias à equipe de suporte. 

- Necessidade 3: Acessar o Histórico de Problemas por Equipamento e Usuário 
-- Descrição: A equipe técnica necessita de uma base de dados acessível e 
pesquisável que armazene o histórico de problemas por equipamento 
(patrimônio) e por usuário. A capacidade de filtrar e consultar esses registros 
de forma rápida é crucial para a rastreabilidade, o diagnóstico eficiente de 
falhas recorrentes e a identificação de padrões, otimizando a manutenção 
preventiva. 

- Necessidade 4: Gerar Indicadores de Desempenho (KPIs) para a Gestão 
-- Descrição: A gerência de T.I. requer dashboards visuais e relatórios 
automáticos (com opções de exportação para Excel/PDF) que apresentem 
Indicadores Chave de Desempenho (KPIs) relevantes. Exemplos incluem tempo 
médio de atendimento (TMA), volume de chamados por categoria, 
equipamentos com maior incidência de falhas e nível de satisfação do usuário. 
Esses KPIs são essenciais para a tomada de decisões estratégicas e a otimização 
contínua dos serviços. 

- Necessidade 5: Manter um Inventário de Ativos de T.I. Confiável e Atualizado 
-- Descrição: A equipe de T.I. necessita de um sistema para manter um inventário 
preciso e atualizado de todos os ativos de tecnologia (hardware e software). 
Isso inclui informações detalhadas sobre localização, responsável, status (em 
uso, em estoque, em manutenção) e histórico de manutenção. Um inventário 
confiável é fundamental para o controle patrimonial, a segurança da 
informação e o planejamento de ciclos de vida dos equipamentos. 

- Necessidade 6: Definir Níveis de Prioridade nos Chamados 
-- Descrição: O sistema deve permitir que o usuário classifique o chamado de 
acordo com a urgência e o impacto no negócio, e que a equipe de T.I possa 
priorizar automaticamente chamados críticos para evitar atrasos em processos 
essenciais. Uma gestão de prioridades clara é vital para otimizar o tempo de 
resposta e a alocação de recursos. 

- Necessidade 7: Registro de Conhecimento (Base de Soluções). 
-- Descrição: Deve existir uma base de conhecimento integrada e de fácil acesso, 
contendo tutoriais, FAQs, artigos de solução de problemas e histórico de 
resoluções. Esta base deve auxiliar tanto os usuários (para autoatendimento) 
quanto os técnicos (para reutilização de soluções já aplicadas), promovendo a 
autonomia e a eficiência. 

- Necessidade 8: Controle de Acordo de Nível de Serviço (SLA). 
-- Descrição: O sistema deve acompanhar e monitorar os prazos de atendimento 
de acordo com os Acordos de Nível de Serviço (SLAs) definidos. O gestor de T.I. 
precisa ter a capacidade de monitorar se os atendimentos estão dentro dos 
tempos acordados, garantindo a conformidade e a qualidade do serviço 
prestado. 

## 3.4 Conclusões

# 4. Tecnologias
## 4.1 Frontend
## 4.2 Backend
## 4.3 Banco de Dados
## 4.4 Deploy
## 4.5 Ferramentas

# 5. Solução Proposta
## 5.1 Descrição geral
## 5.2 Diagrama de arquitetura
## 5.3 Protótipo
## 5.4 Telas

# 6. Justificativas das Decisões

- Uso de um sistema web responsivo (React) – Permite acesso rápido e de qualquer 
dispositivo, atendendo à necessidade de visibilidade e agilidade. 
- Banco de dados relacional (PostgreSQL) – Garante rastreabilidade e integridade das 
informações, atendendo ao requisito de inventário confiável. 
- API Backend (Node.js + Express) – Oferece flexibilidade para implementar as regras 
de negócio e integrações futuras, suportando o crescimento da solução. 
- Relatórios e indicadores – Atendem à necessidade de apoiar decisões estratégicas e 
reduzir falhas recorrentes. 
- Hospedagem em serviços gratuitos (Render/Railway) – Atende à restrição de custo 
zero, mantendo o projeto acessível.

# 7. Conclusão e Próximos Passos

## 7.1 Conexão com proposta inicial

De acordo com o problema inicial que denunciava a falta de agilidade e transparência 
no gerenciamento de chamados de TI, criaremos um sistema centralizado, responsivo e com 
recursos para acompanhamento, análise e tomada de decisão. As funcionalidades que serão 
desenvolvidas devem corresponder às necessidades mapeadas e às dores apontadas, 
garantindo aderência ao escopo e aos objetivos originais. 

## 7.2 Próximos passos

- Realizar testes com técnicos e administradores para verificar usabilidade, clareza das 
informações e tempo de execução das tarefas. 
- Integração com sistemas de e-mail ou chat corporativo para notificações 
automáticas. 
- Sistema de SLA configurável por tipo de chamado. 
- Testes de carga e desempenho. 
- Avaliações de acessibilidade. 
- Preparar um sistema de fácil integração. 

## 7.3 Sugestões
### Aprimoramento das Funcionalidades 
- Ampliação do módulo de relatórios, com dashboards personalizáveis, exportação de dados e 
filtros avançados. 
- Notificações automáticas por e-mail ou sistema interno, informando atualizações de 
chamados ou mudanças de status. 
- Controle de permissões por perfil de usuário (técnico, gestor, administrador, solicitante), 
garantindo acesso adequado às informações. 
- Integração com ferramentas externas, como sistemas de inventário, monitoramento de rede 
ou plataformas de RH. 
- Implementação de SLA (Service Level Agreement) para controle de prazos e níveis de serviço. 
### Segurança da Aplicação 
- Autenticação segura: adoção de JWT com expiração configurada, tokens de renovação e uso 
de HTTPS em toda a comunicação. 
- Criptografia de dados sensíveis: uso de hashing (bcrypt) para senhas e criptografia AES para 
dados confidenciais armazenados. 
- Proteção contra ataques comuns: implementação de medidas contra SQL Injection, Cross-Site 
Scripting (XSS) e Cross-Site Request Forgery (CSRF). 
- Gestão de logs e auditoria: registro de ações dos usuários e eventos críticos para 
rastreabilidade e detecção de anomalias. 
- Backup e recuperação de dados: rotina automatizada de backup no banco de dados, com 
políticas de retenção e testes de restauração. 
### Ciclo de Desenvolvimento Seguro (Secure SDLC) 
- Planejamento com foco em segurança: definição de requisitos de segurança desde a fase de 
análise do sistema. 
- Code Review e testes automatizados: revisão de código por pares e uso de ferramentas de 
análise estática (como SonarQube ou ESLint). 
- Testes de segurança (Pentest e OWASP): simulação de ataques para identificar 
vulnerabilidades e avaliar a resistência do sistema. 
- Integração Contínua e Entrega Contínua (CI/CD): automação do build, testes e deploy com 
ferramentas como GitHub Actions, Jenkins ou GitLab CI. 
- Documentação e controle de versão: registro atualizado das APIs, fluxos de dados e 
dependências, favorecendo manutenção e governança. 
### Escalabilidade e Manutenção 
- Containerização com Docker e futura orquestração com Kubernetes, para facilitar o deploy e 
gerenciamento de ambientes. 
- Monitoramento de desempenho e disponibilidade, com ferramentas como Prometheus, 
Grafana ou LogRocket. 
- Refinamento da arquitetura, migrando para microserviços se o sistema crescer em 
complexidade. 
- Adoção de testes de carga (Load Testing) para avaliar o comportamento sob alto volume de 
chamados e usuários simultâneos.
