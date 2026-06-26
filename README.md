# 💳 Sistema Bancário em C

Projeto desenvolvido em linguagem **C** com o objetivo de simular o funcionamento de um sistema bancário real diretamente no terminal, permitindo operações como criação de conta, login, depósito, saque, transferência, consulta de saldo e extrato bancário.

---

## 📌 Sobre o Projeto

Este projeto foi criado com foco em praticar conceitos fundamentais da programação estruturada utilizando a linguagem C.

A ideia principal foi desenvolver um sistema capaz de gerenciar contas bancárias e realizar operações financeiras de forma segura e organizada, simulando funcionalidades presentes em bancos reais.

Além das operações básicas, o sistema também possui mecanismos de segurança, como autenticação por senha, limite de tentativas de login e bloqueio temporário de contas após várias tentativas incorretas.

---

## 🎯 Objetivos

Durante o desenvolvimento do projeto foram aplicados conceitos importantes da programação, como:

- Programação estruturada
- Organização de código em funções
- Manipulação de arrays (vetores)
- Estruturas condicionais (`if` / `else`)
- Estruturas de repetição
- Manipulação de strings
- Controle de acesso com autenticação
- Validação de dados
- Manipulação de data e hora
- Simulação de regras de negócio de um sistema bancário

---

## ⚙️ Funcionalidades do Sistema

### 📝 Criar Conta

Permite cadastrar uma nova conta bancária.

Informações solicitadas:

- Nome do titular
- Senha de acesso

O sistema gera automaticamente:

- Número da conta
- Saldo inicial zerado

---

### 🔐 Fazer Login

Permite acessar uma conta já cadastrada utilizando:

- Número da conta
- Senha

Regras de segurança:

- Máximo de 3 tentativas
- Após exceder o limite, a conta fica bloqueada por 30 segundos

---

### 💰 Depositar

Permite adicionar saldo à conta logada.

Validações:

- Usuário precisa estar logado
- Valor precisa ser maior que zero
- Sistema solicita confirmação da operação

Após confirmação:

- Saldo é atualizado
- Operação é registrada no histórico

---

### 💸 Sacar

Permite retirar dinheiro da conta.

Validações:

- Usuário precisa estar logado
- Valor deve ser positivo
- Verificação de saldo suficiente

Após a operação:

- Saldo é atualizado
- Histórico é registrado

---

### 🔄 Transferir

Permite enviar dinheiro para outra conta cadastrada.

Validações:

- Usuário precisa estar logado
- Conta destino deve existir
- Não é permitido transferir para a própria conta
- Verificação de saldo disponível

Após a operação:

- Valor removido da conta de origem
- Valor adicionado à conta destino
- Registro salvo no histórico das duas contas

---

### 📊 Consultar Saldo

Mostra informações da conta atualmente logada.

Exibe:

- Nome do titular
- Número da conta
- Saldo atual

---

### 📄 Extrato Bancário

Exibe o histórico das últimas movimentações realizadas na conta.

O sistema armazena até:

- 5 transações recentes

Cada movimentação registra:

- Tipo da operação
- Valor movimentado
- Data e horário

Exemplo:

```text
26/06/2026 14:30 - Depósito de R$ 150.00
26/06/2026 14:45 - Saque de R$ 50.00
```

---

### 🚪 Logout

Permite sair da conta atual sem encerrar o sistema.

Após o logout:

- Nenhuma conta permanece conectada

---

## 🛠 Estrutura do Código

O projeto foi dividido em funções específicas para manter organização e facilitar manutenção.

Funções principais:

| Função | Responsabilidade |
|----------|----------------|
| `criar_conta()` | Criar novas contas |
| `fazer_login()` | Autenticação do usuário |
| `depositar()` | Adicionar saldo |
| `sacar()` | Retirar dinheiro |
| `transferir()` | Transferência entre contas |
| `consultar_saldo()` | Mostrar saldo disponível |
| `extrato()` | Exibir histórico bancário |
| `fazer_logout()` | Encerrar sessão atual |

Funções auxiliares:

| Função | Responsabilidade |
|----------|----------------|
| `buscar_conta()` | Localizar conta pelo número |
| `obter_horario()` | Capturar data e horário |
| `registrar_historico()` | Salvar movimentações |
| `confirmar_operacao()` | Confirmar ações do usuário |

---

## 🔒 Sistema de Segurança

O sistema implementa uma lógica básica de segurança para proteger o acesso às contas.

Regras implementadas:

- Máximo de 3 tentativas de login
- Bloqueio temporário após exceder o limite
- Tempo de bloqueio: 30 segundos

Variáveis responsáveis:

```c
tentativas_login[]
bloqueio_login[]
```

---

## 🧠 Estrutura de Dados

As informações das contas são armazenadas utilizando arrays.

```c
num_conta[]       // Número das contas
nome[][]          // Nome dos usuários
senha[][]         // Senhas cadastradas
saldo[]           // Saldo de cada conta
historico[][][]   // Histórico das transações
```

Controle de sessão:

```c
conta_logada = -1
```

Significado:

- `-1` → Nenhum usuário logado
- Outro valor → Índice da conta atualmente conectada

---

## 🎨 Interface do Sistema

O programa utiliza códigos ANSI para tornar a interface mais organizada visualmente dentro do terminal.

Cores utilizadas:

- 🟢 Verde → Operações realizadas com sucesso
- 🔴 Vermelho → Mensagens de erro
- 🟡 Amarelo → Avisos e confirmações
- 🔵 Ciano → Menus e títulos

---

## 💻 Tecnologias Utilizadas

- Linguagem C
- `stdio.h`
- `string.h`
- `time.h`

---

## 📷 Menu do Sistema

```text
[1] Criar Conta
[2] Fazer Login
[3] Depositar
[4] Sacar
[5] Transferir
[6] Consultar Saldo
[7] Extrato
[8] Fazer Logout
[0] Encerrar Sistema
```

---

## 🚀 Como Executar

Compilar o programa:

```bash
gcc sistema_bancario.c -o banco
```

Executar:

```bash
./banco
```

---

## 👨‍💻 Desenvolvedores

Projeto desenvolvido por:

- Melissa Felix  
- Gabrielly Figueiredo  
- Pedro de Brito  

---

## 📚 Aprendizados

Este projeto permitiu aplicar conhecimentos importantes em programação, principalmente no desenvolvimento de lógica estruturada e construção de sistemas baseados em regras reais.

Foram trabalhados conceitos como:

- Estruturação de código
- Organização em funções
- Segurança em autenticação
- Manipulação de dados
- Controle de fluxo
- Simulação de sistema bancário real

---

## ⭐ Projeto Acadêmico

Projeto desenvolvido com fins educacionais para estudo da linguagem C e desenvolvimento da lógica de programação.
