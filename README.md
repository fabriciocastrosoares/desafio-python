# Desafio: Modelando um Sistema Bancário

## 📋 Descrição do Projeto

Este projeto implementa um **sistema bancário em Python** utilizando **Programação Orientada a Objetos (POO)** com conceitos como herança, encapsulamento, abstração e polimorfismo.

O sistema permite que clientes realizem operações bancárias básicas como depósitos, saques e consulta de extrato, com validações de limite e quantidade de saques.

---

## 🎯 Objetivos

- ✅ Aplicar conceitos fundamentais de POO (classe, herança, encapsulamento)
- ✅ Implementar abstrações com classes abstratas
- ✅ Validar regras de negócio (limites, saques, saldo)
- ✅ Manter histórico de transações
- ✅ Criar uma interface interativa por menu

---

## 🏗️ Estrutura das Classes

### **Cliente**
- Base para clientes do banco
- Atributos: `endereco`, `contas`
- Métodos: `realizar_transacao()`, `adicionar_conta()`

### **PessoaFisica** (herda de Cliente)
- Cliente pessoa física
- Atributos: `nome`, `data_nascimento`, `cpf`

### **Conta**
- Classe base para contas bancárias
- Atributos: `saldo`, `numero`, `agencia`, `cliente`, `historico`
- Métodos: `sacar()`, `depositar()`

### **ContaCorrente** (herda de Conta)
- Conta com limite e limite de saques
- Atributos: `limite`, `limite_saques`
- Validações específicas para saques

### **Historico**
- Registra todas as transações da conta
- Armazena: tipo, valor e data/hora da transação

### **Transacao** (classe abstrata)
- Define interface para transações
- Propriedade abstrata: `valor`
- Método abstrato: `registrar()`

### **Saque e Deposito** (herdam de Transacao)
- Implementações concretas de transações
- Registram operações no histórico

---

## 💰 Funcionalidades

| Opção | Descrição |
|-------|-----------|
| **[d]** Depositar | Deposita valor em uma conta |
| **[s]** Sacar | Realiza saque com validações |
| **[e]** Extrato | Exibe histórico e saldo atual |
| **[nc]** Nova Conta | Cria nova conta corrente |
| **[lc]** Listar Contas | Lista todas as contas cadastradas |
| **[nu]** Novo Usuário | Cadastra novo cliente |
| **[q]** Sair | Encerra o programa |

---

## 🔒 Regras de Negócio

- **Saque**: Não pode exceder o saldo + limite
- **Limite de Saques**: Máximo 3 saques por conta
- **Depósito**: Apenas valores positivos
- **Transações**: Registram data/hora com precisão de segundos
- **Agência**: Padrão "0001" para todas as contas

---

## 🚀 Como Usar

1. **Execute o programa**:
   ```bash
   python desafio.py
   ```

2. **Crie um usuário**:
   - Opção `[nu]`
   - Informe CPF, nome, data de nascimento e endereço

3. **Crie uma conta**:
   - Opção `[nc]`
   - Informe o CPF do cliente cadastrado

4. **Realize transações**:
   - Deposite (opção `[d]`)
   - Saque (opção `[s]`) - máximo 3 saques
   - Consulte extrato (opção `[e]`)

---

## 🔧 Tecnologias e Conceitos

- **Python 3.7+**
- **Programação Orientada a Objetos (POO)**
  - Herança (`class ContaCorrente(Conta)`)
  - Encapsulamento (atributos privados com `_`)
  - Abstração (classe `Transacao` com métodos abstratos)
  - Polimorfismo (métodos `registrar()` implementados diferentemente)
- **Properties** para acesso controlado a atributos
- **Métodos de classe** (`@classmethod`)
- **Datetime** para timestamp de transações

---

## 📝 Exemplo de Uso

```
================ MENU ================
[d]	Depositar
[s]	Sacar
[e]	Extrato
[nc]	Nova conta
[lc]	Listar contas
[nu]	Novo usuário
[q]	Sair
=> nu

Informe o CPF (somente número): 12345678900
Informe o nome completo: João Silva
Informe a data de nascimento (dd-mm-aaaa): 15-06-1990
Informe o endereço (logradouro, nro - bairro - cidade/sigla estado): Rua A, 123 - Centro - São Paulo/SP

=== Cliente criado com sucesso! ===
```

---


## 📚 Conceitos-Chave Implementados

| Conceito | Implementação |
|----------|---------------|
| **Herança** | PessoaFisica herda de Cliente; ContaCorrente herda de Conta |
| **Encapsulamento** | Atributos privados (`_saldo`, `_numero`, etc.) com properties |
| **Abstração** | Classe Transacao define interface sem implementação |
| **Polimorfismo** | Saque e Deposito implementam `registrar()` diferentemente |
| **Composição** | Conta contém Historico; Cliente contém lista de Contas |

---

## 👨‍💻 Autor

Desafio realizado como exercício de aprendizado em POO com Python.
