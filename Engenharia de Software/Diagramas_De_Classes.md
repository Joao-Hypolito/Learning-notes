# 📌 Aula 5: Diagramas de Classes I — A Estrutura Estática do Sistema

Este repositório contém o resumo detalhado da **Aula 5** da disciplina de Engenharia de Software II (FHO - Sistemas de Informação). O foco desta aula é a especificação interna das classes: anatomia, visibilidades, atributos tipados e operações.

---

## 🧠 Conteúdo Resumido

### 1. Transição: Do Comportamento Dinâmico à Estrutura Estática

Nas aulas anteriores, o foco foi **o que o sistema faz** (comportamento dinâmico: *User Stories*, *Casos de Uso*, *Diagramas de Atividades*). A partir de agora, o foco passa a ser **do que o sistema é feito** (estrutura estática).

* **Diagrama de Classes:** Espinha dorsal do projeto orientado a objetos. Representa as entidades do domínio, seus dados e suas responsabilidades.
* **Aplicações:** Serve como base direta para a codificação e para a modelagem do banco de dados (Relacional ou NoSQL).

---

### 📦 2. Anatomia da Classe (O Retângulo de 3 Seções)

Uma classe em UML é graficamente representada por um retângulo dividido em três seções verticais:

1. **Seção 1 — Nome da Classe:** Substantivo no singular, escrito em **negrito**. Caso a classe seja abstrata, o nome deve ser grafado em *itálico*.
2. **Seção 2 — Atributos:** Dados que cada objeto armazena.
3. **Seção 3 — Operações (Métodos):** Comportamentos e responsabilidades que a classe sabe executar.

> ⚠️ **Membro Estático (`static`):** Quando um atributo ou método pertence à **classe** e não às instâncias (objetos), a sua assinatura deve ser **sublinhada** (ex.: <u>`+ contarFrota() : int`</u>).

---

### 🛡️ 3. Visibilidades (Encapsulamento)

As visibilidades definem quem tem permissão para acessar cada membro da classe:

| Símbolo | Visibilidade | Descrição |
| :---: | :--- | :--- |
| **`+`** | **Public** | Acessível por qualquer classe do sistema. |
| **`-`** | **Private** | Acessível **exclusivamente** dentro da própria classe. |
| **`#`** | **Protected** | Acessível pela própria classe e por suas subclasses. |
| **`~`** | **Package** | Acessível apenas por classes dentro do mesmo pacote/módulo. |

> 🚨 **Regra de Ouro do Encapsulamento:** Atributo **NUNCA** deve ser `public` sem uma justificativa explícita de arquitetura. O padrão absoluto é usar `private` ou `protected` combinados com métodos de acesso explícitos (getters/setters).

---

### 🖊️ 4. Sintaxe e Tipagem de Atributos

Toda especificação de atributo deve seguir a sintaxe estrita da UML:

$$\text{visibilidade } \text{nomeAtributo} : \text{Tipo} [\text{multiplicidade}] = \text{valorInicial}$$

* **Exemplo Completo:** `- tarifaBase : Money [1] = R$ 5,00`
* **Convenção de Nome:** Padrão `camelCase`.
* **Tipos Primitivos:** `int`, `float`, `boolean`, `char`.
* **Tipos Complexos e Enums:** `Money`, `LocalDate`, `TipoVeiculo {BICICLETA, PATINETE}`.
* **Tipagem Forte:** Todo atributo **deve** possuir seu tipo declarado. Atributos sem tipo invalidam o modelo técnico.

---

### ⚙️ 5. Operações (Métodos) e Análise Textual

As operações representam os verbos de ação extraídos dos cenários e regras de negócio.

**Sintaxe da Operação:**
$$\text{visibilidade } \text{nomeMetodo}(\text{parametro} : \text{Tipo}) : \text{TipoRetorno}$$

* **Exemplo:** `+ encerrar(estacao : Estacao) : Recibo`

#### Origem dos Elementos (Análise Textual)
* **Substantivos** $\longrightarrow$ Erguem-se como **Classes Candidatas** ou **Atributos** (ex.: *Usuário*, *Veículo*, *Estação*).
* **Verbos** $\longrightarrow$ Transformam-se em **Operações/Métodos** na classe correta que detém a responsabilidade (ex.: *reservar()*, *devolver()*).
* **Adjetivos/Estados** $\longrightarrow$ Viram **Atributos Tipados** (ex.: *disponivel : boolean*, *bloqueado : boolean*).

---

### ❌ Erros Críticos que Invalidações de Modelos

1. **Atributo Público:** Viola o encapsulamento básico (`+ saldo : float`).
2. **Classe "Deus" (God Class):** Classes como `Gerenciador` ou `Sistema` concentrando dezenas de responsabilidades sem coesão.
3. **Atributo sem Tipo:** Omitir a tipagem de um atributo (`- tarifa`).
4. **Método na Classe Errada:** Alocar métodos fora do contexto de seus dados (ex.: colocar `calcularValorCorrida()` na classe `Usuario` em vez da classe `Corrida`).

---

### 🔗 Rastreabilidade e Mapeamento

$$\text{Cenário BDD / Caso de Uso (Verbo)} \longrightarrow \text{Análise Textual} \longrightarrow \text{Operação na Classe (Método UML)}$$