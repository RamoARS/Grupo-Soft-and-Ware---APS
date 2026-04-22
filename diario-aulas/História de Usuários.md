# Histórias de Usuário
### Aula 8 — 08/04/2026

---

## Login

**Como** administrador do sistema  
**Quero** acessar o sistema com minha conta exclusiva  
**Para** que minhas ações sejam registradas e eu tenha as permissões necessárias para operar a plataforma

> Dado que eu sou um administrador cadastrado e estou na página de login  
> Quando eu insiro meu e-mail e senha válidos e clico no botão "Entrar"  
> Então o sistema deve autenticar minhas credenciais

> Dado que estou na página de login  
> Quando eu insiro um usuário válido, mas uma senha incorreta  
> Então o sistema deve exibir a mensagem de erro: "Usuário ou senha inválidos"

---

## Cadastro de Usuários

**Como** atendente da biblioteca  
**Quero** realizar o cadastro de um usuário não registrado no sistema  
**Para** que ele possua um registro no sistema

> Dado que é necessário verificar se o aluno já possui conta  
> Quando for realizar o cadastro do aluno  
> Então o sistema deve disponibilizar uma sessão de busca por Nome, CPF e Tipo

> Dado que todas as contas de usuário possuem informações cadastrais  
> Quando a atendente for efetivar o cadastro  
> Então o sistema deve solicitar as seguintes informações: nome completo, CPF, email, telefone, RA e vínculo institucional

> Dado que o cadastro precisa do CPF  
> Quando for inserido um CPF inválido  
> Então o sistema avisa que o CPF está inválido

> Dado que o cadastro do usuário for efetivado e verificado pelo sistema  
> Quando realizado pela atendente  
> Então o sistema deve registrar a data de cadastro e o status "Ativo" do usuário

> Dado que foi inserido informações erradas na conta  
> Quando foi realizado o cadastro do aluno  
> Então o sistema deve disponibilizar uma opção de editar conta, para alterar suas informações cadastrais

---

## Cadastro de Livros

**Como** bibliotecária chefe  
**Quero** adicionar um novo registro no acervo de livros  
**Para** criar uma representação do livro no sistema

> Dado que todos os livros possuem informações de cadastro  
> Quando for iniciado um novo registro  
> Então o sistema deve solicitar as seguintes informações: título, autor, editora, ano, ISBN, categoria, o código de tombo e a condição de conservação do primeiro exemplar e opcionalmente uma imagem do livro

---

**Como** bibliotecária chefe  
**Quero** editar as informações de um livro já cadastrado  
**Para** manter os dados atualizados

> Dado que o livro já está cadastrado  
> Quando a opção de editar livro for acessada  
> Então o sistema deve permitir a alteração das seguintes informações: título, autor, editora, ano, ISBN, categoria e a imagem do livro

> Dado que alguns livros possuem mais de um exemplar  
> Quando a área de exemplares for acessada  
> Então o sistema deve permitir a adição de outro exemplar, solicitando o código de tombo e a condição de conservação do exemplar

> Dado que alguns livros possuem mais de um exemplar  
> Quando a opção de editar exemplares for acessada  
> Então o sistema deve permitir a alteração do código de tombo e da condição de conservação do exemplar

---

## Fluxo de Empréstimo

### Aluno

**Como** aluno  
**Quero** fazer um empréstimo  
**Para** realizar um estudo

> Dado que o aluno escolhe um exemplar de um livro disponível no acervo  
> Quando ele executa o empréstimo  
> Então o sistema muda seus status para emprestado, associa ao aluno e exibe a data de devolução calculada para 7 dias após o empréstimo

> Dado que o aluno escolha um livro sem exemplares disponíveis  
> Quando ele busca por um exemplar  
> Então o sistema mostra a indisponibilidade do livro

> Dado que o aluno não sabe o nome do livro  
> Quando sabe o autor  
> Então o sistema exibe todos os livros do autor

> Dado que o aluno não sabe o nome do livro  
> Quando sabe o ano  
> Então o sistema exibe todos os livros daquele ano

> Dado que o aluno não sabe o nome do livro  
> Quando sabe sua categoria  
> Então o sistema exibe todos os livros daquela categoria

> Dado que o aluno tente emprestar um livro  
> Quando ele já emprestou 2 livros simultâneos  
> Então o sistema avisa que já foi atingido o número limite de empréstimo

> Dado que o aluno empreste um livro  
> Quando o sistema confirma o empréstimo  
> Então imprime um comprovante de empréstimo e envia ao e-mail do aluno

---

### Funcionário

**Como** funcionário da biblioteca  
**Quero** fazer um empréstimo  
**Para** ler o livro

> Dado que o funcionário tente emprestar um livro  
> Quando ele já emprestou 3 livros simultâneos  
> Então o sistema avisa que já foi atingido o número limite de empréstimo

> Dado que o funcionário escolhe um exemplar de um livro disponível no acervo  
> Quando ele executa o empréstimo  
> Então o sistema muda seus status para emprestado, associa ao funcionário e exibe a data de devolução calculada para 10 dias após o empréstimo

---

### Professor

**Como** professor  
**Quero** fazer um empréstimo  
**Para** preparar uma aula

> Dado que o professor escolhe um exemplar de um livro livre no acervo  
> Quando ele executa o empréstimo  
> Então o sistema muda seus status para emprestado, associa ao professor e exibe a data de devolução calculada para 15 dias após o empréstimo

> Dado que o professor tente emprestar um livro  
> Quando ele já emprestou 5 livros simultâneos  
> Então o sistema avisa que já foi atingido o número limite de empréstimo

---

### Diretor

**Como** diretor  
**Quero** fazer um empréstimo  
**Para** ler o livro

> Dado que o diretor escolhe um exemplar de um livro disponível no acervo  
> Quando ele executa o empréstimo  
> Então o sistema muda seus status para emprestado, associa ao diretor, mas não impõe uma data de devolução limite por conta do seu cargo

> Dado que o diretor tente emprestar um livro  
> Quando ele já tem 2 ou mais livros emprestados  
> Então o sistema não limita os empréstimos do diretor por conta do seu cargo

---

## Fluxo de Devolução

### Aluno

**Como** aluno  
**Quero** levar um exemplar emprestado até a biblioteca  
**Para** realizar uma devolução

> Dado que o aluno devolve o exemplar emprestado  
> Quando o exemplar volta ao acervo  
> Então o sistema altera o status do exemplar para disponível e desassocia ao aluno

> Dado que o aluno devolva um exemplar emprestado  
> Quando o sistema confirmar a devolução  
> Então o sistema imprime um comprovante de devolução e envie ele ao e mail do aluno

> Dado que o aluno devolve um exemplar danificado  
> Quando o funcionário indicar que o exemplar está danificado  
> Então o sistema salva que aquele exemplar está danificado e o aluno que danificou

> Dado que o aluno devolve um livro  
> Quando esse exemplar possuir uma reserva ativa  
> Então o sistema notifica que esse livro possui uma reserva e o aluno que reservou

> Dado que o aluno perca o livro  
> Quando informar a bibliotecária  
> Então o sistema salva aquele exemplar como perdido e associa ao aluno

> Dado que o aluno perca o livro  
> Quando não se lembrar qual livro era  
> Então o sistema deve permitir pesquisar pelos dados do aluno

---

### Funcionário

**Como** funcionário  
**Quero** fazer o processo de devolução  
**Para** devolver um livro emprestado a biblioteca

> Dado que o funcionário queira realizar a devolução  
> Quando for pesquisar o livro no sistema  
> Então o sistema deve permitir pesquisar pelo seu código de tombo

---

## Renovações

### Aluno

**Como** aluno  
**Quero** fazer a renovação de um empréstimo  
**Para** prorrogar a data de devolução

> Dado que o aluno deseja renovar um empréstimo  
> Quando a renovação é confirmada pelo sistema  
> Então o sistema calcula, altera e exibe a nova data de devolução como 7 dias após a renovação

> Dado que o aluno deseja renovar um empréstimo  
> Quando há uma reserva ativa para o livro  
> Então o sistema deve impedir a renovação

> Dado que o aluno deseja renovar um empréstimo  
> Quando já foi feita uma renovação desse mesmo empréstimo  
> Então o sistema deve impedir a renovação

> Dado que o livro emprestado está atrasado  
> Quando o aluno tenta realizar a renovação  
> Então o sistema deve impedir a renovação e cobrar a multa

---

### Funcionário

**Como** funcionário da biblioteca  
**Quero** fazer a renovação de um empréstimo  
**Para** prorrogar a data de devolução

> Dado que o funcionário deseja renovar um empréstimo  
> Quando a renovação é confirmada pelo sistema  
> Então o sistema calcula, altera e exibe a nova data de devolução como 10 dias após a renovação

---

### Professor

**Como** professor  
**Quero** fazer a renovação de um empréstimo  
**Para** prorrogar a data de devolução

> Dado que o professor deseja renovar um empréstimo  
> Quando a renovação é confirmada pelo sistema  
> Então o sistema calcula, altera e exibe a nova data de devolução como 15 dias após a renovação

> Dado que o professor deseja renovar um empréstimo  
> Quando há uma reserva ativa para o livro  
> Então o sistema deve permitir a renovação, independente da fila de reservas

---

## Reservas

### Aluno

**Como** aluno  
**Quero** reservar um livro que está atualmente emprestado  
**Para** poder emprestá-lo quando ele estiver disponível

> Dado que existe uma fila de reservas ordenada pela data de solicitação  
> Quando o livro fica disponível  
> Então o sistema deve disponibilizar o empréstimo para o primeiro usuário na fila de reservas

> Dado que o livro fica disponível no sistema  
> Quando há uma reserva para ele  
> Então o sistema deve notificar por email o primeiro usuário na fila de reservas, informando a disponibilidade do livro - Devolução

> Dado que o aluno foi notificado por email sobre a disponibilidade de um livro reservado - Devolução  
> Quando a notificação é enviada  
> Então o aluno que reservou possui 3 dias para buscá-lo, antes da reserva expirar - Devolução

> Dado que o aluno não buscou o livro  
> Quando já passaram os 3 dias  
> Então o próximo aluno da fila é notificado - Empréstimo

> Dado que o aluno tente realizar uma reserva  
> Quando ele já possui 2 reservas ativas de diferentes livros  
> Então o sistema deve informar que o número máximo de reservas já foi atingido - Empréstimo

---

### Funcionário

**Como** funcionário da biblioteca  
**Quero** reservar um livro que está atualmente emprestado  
**Para** poder emprestá-lo quando ele estiver disponível

> Dado que o funcionário tente realizar uma reserva  
> Quando já possui 3 reservas ativas de diferentes livros  
> Então o sistema deve informar que o número máximo de reservas já foi atingido - Empréstimo

---

### Professor

**Como** professor  
**Quero** reservar um livro que está atualmente emprestado  
**Para** poder emprestá-lo quando ele estiver disponível

> Dado que o livro fica disponível no sistema  
> Quando há reservas para ele que não foram feitas por outros professores  
> Então o professor pode emprestá-lo, independente da fila de reservas - Empréstimo

> Dado que o professor tente realizar uma reserva  
> Quando já possui 5 reservas ativas de diferentes livros  
> Então o sistema deve informar que o número máximo de reservas já foi atingido

---

## Multas e Atrasos

### Aluno — Bloqueio por pendência

**Como** aluno  
**Quero** que o sistema informe quando um usuário estiver bloqueado  
**Para** barrar quaisquer ações do sistema antes de resolver a pendência

> Dado que o aluno possua um livro emprestado  
> Quando não realizar a devolução conforme a data informada  
> Então o sistema deve calcular a multa R$1,00 por dia de atraso e registrar o status *Bloqueado*

> Dado que o aluno possui multa pendente  
> Quando tentar realizar um empréstimo  
> Então o sistema bloqueará a operação e informará a multa pendente

> Dado que o aluno possui multa pendente  
> Quando tentar realizar uma reserva  
> Então o sistema bloqueará a operação e informará a multa pendente

> Dado que vários alunos possuem pendências  
> Quando for verificado na sessão de atrasos e pendências  
> Então o sistema deve apresentar um botão de exibir que apresente a lista completa de alunos com pendências

---

### Aluno — Notificação de atraso

**Como** aluno  
**Quero** receber notificação de atraso  
**Para** organizar minha agenda e gerenciar o controle de pendências

> Dado que o aluno foi bloqueado por uma pendência  
> Quando o bloqueio for aplicado  
> Então o usuário deverá ser notificado por email

> Dado que o aluno possui um empréstimo com data vencida  
> Quando se passar 1 dia do último aviso de vencimento  
> Então o sistema deve enviar um email com: nome do livro, data de vencimento, quantos dias de atraso e valor da multa acumulada

---

### Funcionário — Registrar pagamento de multa

**Como** funcionário  
**Quero** registrar pagamento da multa  
**Para** remover pendência do usuário

> Dado que o usuário possui multa em dinheiro  
> Quando o operador registrar pagamento  
> Então o sistema deve registrar o meio de pagamento, salvar o funcionário, data e hora e remover o bloqueio de usuário

---

### Funcionário — Aplicar isenção

**Como** funcionário  
**Quero** aplicar isenção  
**Para** resolver casos especiais

> Dado que o aluno possui multa e há autorização do funcionário  
> Quando o funcionário aplicar isenção  
> Então o sistema deve zerar a multa e desbloquear o usuário

---

### Funcionário — Registrar multa por danificação

**Como** funcionário  
**Quero** registrar multa por danificação  
**Para** cobrar os danos ao livro

> Dado que o livro foi devolvido danificado  
> Quando o funcionário responsável avaliar o dano  
> Então o sistema deve permitir informar valor da multa e gerar pendência para o usuário que devolveu o livro danificado
