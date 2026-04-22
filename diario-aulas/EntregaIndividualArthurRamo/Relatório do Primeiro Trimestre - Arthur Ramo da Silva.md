# Relatório do Primeiro Trimestre - Arthur Ramo da Silva
### Grupo Soft and Ware

---

## Aula 1
Na primeira aula foi-se aprendido como funciona o planejamento de um projeto, passando por validações e verificações para alcançar um protótipo. Em uma empresa, busca-se profissionais com competência em analisar os projetos, organizar as ideias e planejamento para minimizar as falhas e prejuízos ao longo do desenvolvimento do projeto, possuindo Soft Skills(habilidades de desenvolvimento e cooperação em grupo) e Habilidades técnicas(conhecimentos técnicos para elaborar os sistemas). Empresas valorizam mais especialistas com Soft Skills, para tornar possível o ecossistema(ambiente em que os profissionais cooperam entre si em prol do refino contínuo do projeto) dos projetos.

---

## Aula 2
Na segunda aula foi-se abordado o conceito de valor agregado no desenvolvimento de software, onde a execução é a parte principal do processo mas demanda um planejamento prévio organizado, que não precisa ser completo para economizar tempo, passando por validações até chegar na implementação. Foram apresentados três Ciclos de Vida de Desenvolvimento de Software(SDLCs), sendo eles o Cascata(modelo tradicional e sequencial, ideal para requisitos bem definidos, porém com pouca interação com o cliente e alto risco em caso de erros iniciais), o Ágil(modelo iterativo focado em entregas contínuas e feedbacks constantes) e a Prototipagem(modelo voltado a validar as ideias do cliente por meio de versões iniciais e simplificadas do software). Também foram introduzidas Metodologias Ágeis como Scrum(framework de gestão de entrega de valor por sprints), Kanban(organização de tarefas) e XP(metodologia completa focada em comunicação e feedbacks), todas baseadas no Manifesto Ágil, que prioriza entregar um produto rapidamente com qualidade e adaptação às mudanças do cliente.

---

## Aula 3
Na terceira aula foi-se abordado o Levantamento de Requisitos, etapa inicial do desenvolvimento de software que antecede a Análise, Modelagem, Codificação, Teste, Implantação e Manutenção, sendo recomendadas ao menos três validações ao longo da execução. Foram apresentadas técnicas de elicitação como Entrevista(discussão direta com o cliente), Questionário(coleta simples de requisitos de múltiplas pessoas), Observação(inserção do engenheiro no contexto de uso do sistema), Análise de Documentos(estudo dos materiais já utilizados pela empresa), Brainstorm(geração colaborativa de ideias sem julgamentos), JAD(reuniões estruturadas para decisões por consenso), Prototipagem(versões iniciais do produto para validar ideias com o cliente) e Estudo Etnográfico(registro de comportamentos reais no meio pesquisado), cada uma com vantagens e limitações, devendo ser escolhida conforme o contexto do projeto.

---

## Aula 4
Na quarta aula foi-se abordado o Planejamento da Entrevista, onde o grupo desenvolveu uma estratégia de levantamento de requisitos para um sistema bibliotecário, cujo escopo envolve Gestão de Livros, Cadastramento de Usuários, Automatização de Processos e Segurança, combinando as técnicas de Entrevista, Análise de Documentos e Questionário. O questionário foi estruturado com perguntas voltadas aos processos de usuários, empréstimos, devoluções, reservas, acervo, relatórios, segurança e infraestrutura, enquanto a entrevista foi organizada com perguntas categorizadas por prioridade(Essencial, Importante e Relevante) para garantir que os pontos mais críticos fossem cobertos dentro do tempo disponível. Também foram definidos os papéis dos integrantes na entrevista, divididos entre Entrevistadores, Anotadores e Auxiliar.

---

## Aula 5
Na quinta aula foi-se abordado o Refinamento do Levantamento de Requisitos, onde o grupo organizou e analisou as respostas obtidas na entrevista com as funcionárias da biblioteca Julia, Rosa e Ana, categorizando-as por cores para indicar o nível de confiabilidade de cada resposta(verde para bem respondidas, amarelo para incertas e vermelho para incorretas), realizando triangulações entre as conflitantes. Com isso foi possível mapear os principais fluxos do sistema atual como Cadastro de Usuários, Empréstimo, Devolução, Renovação, Reservas e Multas, identificando limitações do sistema BiblioFIP como a ausência de notificações automáticas, o controle de reservas feito em caderno físico e travamentos frequentes em períodos de maior fluxo. A partir dessas lacunas, o grupo elaborou um novo questionário direcionado a cada funcionária para refinar informações sobre relatórios, regras de perfis de usuário, limites de renovação e formas de pagamento de multas.

---

## Aula 6
Na sexta aula foi-se continuado o refinamento do levantamento de requisitos, coletando e consolidando as respostas do segundo questionário com as funcionárias. Foram definidos os três níveis de acesso dos operadores(Estagiário, Atendente Sênior e Bibliotecária Chefe), as regras específicas do perfil de Diretor(sem prazo, multa ou limite de itens), os cinco relatórios necessários ao sistema(emitidos em PDF e Excel), os limites de reserva por perfil(aluno até 2, funcionário até 3 e professor até 5) e as formas de pagamento de multas(dinheiro, PIX e cartão), além de confirmar-se que o sistema funcionará apenas na rede interna da instituição sem acesso remoto. A partir das lacunas restantes, elaborou-se um novo questionário para ser aplicado em uma sessão JAD.

---

## Aula 7
Na sétima aula foi-se realizada a entrevista final por meio do JAD, onde o grupo aplicou o questionário com perguntas priorizadas por nível de importância. Obteve-se respostas sobre a gestão de danificação de livros(sem valor fixo, analisada conforme o grau do dano e registrada como pendência vinculada ao usuário), a gestão financeira das multas(onde o sistema apenas registra o status e o vínculo com o usuário, sendo o pagamento confirmado por um operador com registro de data, hora e responsável), as permissões dos operadores(definidas por perfil administrativamente, sem alterações por ausência de outros), a compatibilidade com leitores de código de barras(onde o sistema deve aceitar entrada por qualquer meio, sendo a compra do equipamento uma decisão administrativa) e os critérios de busca do acervo(título com busca parcial, autor, código de tombo e categoria, com filtros de temática e disponibilidade). Com isso encerrou-se o ciclo de entrevistas, consolidando as informações necessárias para a definição dos requisitos do sistema.

---

## Aula 8
Na oitava aula foi-se desenvolvido as Histórias de Usuário, que consistem em descrições das funcionalidades do sistema sob a perspectiva de cada tipo de usuário, seguindo o modelo "Como [usuário] / Quero [objetivo] / Para [valor]" com cenários no formato "Dado que [contexto] / Quando [algo acontece] / Então [resultado]". Foram elaboradas histórias para os fluxos de Cadastro de Usuários, Níveis de Acesso, Cadastro de Livros, Empréstimo, Devolução, Renovação, Reservas e Multas, desenvolvidas separadamente para cada perfil(Aluno, Funcionário, Professor, Diretor, Estagiário, Atendente Sênior e Bibliotecária Chefe), onde a história do aluno serviu como base completa e as demais contemplaram apenas as diferenças de cada perfil, como prazos, limites de empréstimo e permissões distintas.

---

## Aula 9
Na nona aula foi-se iniciada a Prototipagem do sistema, onde o grupo utilizou o Figma para prototipar as telas do projeto, tendo como base principal as Histórias de Usuário da aula anterior para guiar a criação das interfaces, garantindo que as funcionalidades e fluxos levantados ao longo das entrevistas fossem corretamente representados no protótipo.
