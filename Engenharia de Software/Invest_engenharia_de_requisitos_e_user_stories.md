# 📌 Aula 2: Engenharia de Requisitos & User Stories

Este repositório contém o resumo detalhado da **Aula 2** sobre Engenharia de Requisitos, Histórias de Usuário (*User Stories*), Critério INVEST e BDD (*Behavior-Driven Development*).

---

## 🧠 Conteúdo Resumido

### 1. Engenharia de Requisitos: O que o software DEVE fazer

A **Engenharia de Requisitos** é a disciplina responsável por descobrir, analisar, documentar e manter as necessidades dos *stakeholders*.

* **Requisitos Funcionais (RF):** Descrevem o **comportamento** e as **funcionalidades** do sistema (*o que o sistema faz*).
  * *Exemplo:* *"O sistema deve permitir que o aluno visualize suas notas."*
* **Requisitos Não-Funcionais (RNF):** Descrevem as **qualidades**, **restrições** e **atributos de desempenho** do sistema (*como o sistema deve ser*).
  * *Exemplo:* *"A API de pagamentos deve responder em menos de 200ms sob pico de acesso."*

---

### 📝 2. User Stories (Histórias de Usuário)

Representam pequenas entregas de valor escritas sob a perspectiva do usuário final, muito utilizadas em metodologias ágeis (Scrum/Kanban).

**Formato Padrão:**
> **Como** `[tipo de usuário]`  
> **Quero** `[ação / funcionalidade]`  
> **Para** `[benefício / valor de negócio]`  

---

### 💎 3. O Checklist INVEST

Para garantir que uma *User Story* tenha qualidade técnica e de negócio antes de entrar em uma *Sprint*, ela deve atender ao acrônimo **INVEST**:

| Letra | Conceito | Descrição |
| :---: | :--- | :--- |
| **I** | **Independent** (Independente) | A história não deve depender diretamente de outra para ser desenvolvida ou testada. |
| **N** | **Negotiable** (Negociável) | Não é um contrato rígido; os detalhes são discutidos entre a equipe e o Product Owner (PO). |
| **V** | **Valuable** (Valiosa) | Deve agregar valor claro para o usuário final ou para o negócio. |
| **E** | **Estimable** (Estimável) | A equipe de desenvolvimento deve conseguir mensurar o esforço necessário para implementá-la. |
| **S** | **Small** (Pequena) | Deve caber confortavelmente em uma única Sprint (geralmente de 1 a 2 semanas). |
| **T** | **Testable** (Testável) | Deve possuir critérios claros para validar se a funcionalidade funciona como esperado. |

---

### 🧪 4. BDD (Behavior-Driven Development) & Gherkin

O BDD conecta a visão do negócio com os testes automatizados utilizando uma linguagem natural estruturada chamada **Gherkin**.

**Estrutura do Cenário de Teste:**

```gherkin
Cenário: Autenticação bem-sucedida de usuário
  Dado que o usuário está na tela de login
  Quando ele preencher os campos com e-mail e senha válidos
  E clicar no botão "Entrar"
  Então o sistema deve redirecioná-lo para a tela principal
  E exibir a mensagem de boas-vindas
```

---

### 🔗 Rastreabilidade

$$\text{User Story (US)} \longrightarrow \text{Caso de Uso (UC)} \longrightarrow \text{Cenários Gherkin (Testes)}$$