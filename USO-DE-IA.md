# Uso de Inteligência Artificial

## 1. Ferramentas utilizadas

Durante o desenvolvimento do trabalho, foram utilizadas ferramentas de Inteligência Artificial como apoio à pesquisa, organização e revisão do conteúdo.

| Ferramenta  | Utilização                                                                                                                    |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **ChatGPT** | Pesquisa orientada, explicação de conceitos, organização do brief, criação e revisão de exemplos de código e revisão textual. |

A IA foi utilizada como ferramenta de apoio. As informações produzidas foram posteriormente comparadas com a documentação oficial do Rust antes de serem incluídas no trabalho.

---

## 2. Partes geradas ou auxiliadas por IA

A IA foi utilizada principalmente nas seguintes partes:

* Estruturação do conteúdo do brief;
* Explicação dos quatro critérios de avaliação: legibilidade, redigibilidade, confiabilidade e custo;
* Explicação de nomes, escopos e tempo de vida;
* Explicação de closures e gerenciamento de memória;
* Classificação do sistema de tipos do Rust;
* Explicação sobre equivalência nominal, inferência de tipos e coerções;
* Criação inicial dos exemplos de código;
* Revisão e simplificação do texto;
* Organização deste documento de auditoria.

A versão final do conteúdo não foi aceita automaticamente. Os integrantes revisaram as informações e verificaram os exemplos antes de utilizá-los.

---

# 3. Prompts principais utilizados

## Prompt 1 — Pesquisa e análise

> "Utilize seu conhecimento de Rust contido na documentação oficial para fazer um brief com os seguintes critérios: avaliação da linguagem pelos quatro critérios da aula 01: legibilidade, redigibilidade, confiabilidade e custo; descrição do modelo de nomes, escopos e tempo de vida; descrição do sistema de tipos; e pelo menos três exemplos executáveis."

**Objetivo:** obter uma primeira estrutura para o conteúdo teórico do trabalho.

---

## Prompt 2 — Simplificação

> "Estruture de maneira mais simplificada, para mim pôr em um docs de até 4 páginas. Mas quero que você apenas me passe o conteúdo, eu que montarei o documento."

**Objetivo:** reduzir e reorganizar o conteúdo para atender ao limite de páginas.

---

## Prompt 3 — Exemplos executáveis

> "Todo trecho de código do brief precisa rodar de verdade; diga como executá-lo. Exemplo sem execução comprovada não conta."

**Objetivo:** garantir que os exemplos apresentados pudessem ser testados na prática.

---

## Prompt 4 — README

> "Faça um README.md para o GitHub no qual irá falar sobre a ideia do trabalho e os componentes do grupo"

**Objetivo:** criar a documentação inicial do repositório.

---

# 4. Auditoria do conteúdo gerado

A auditoria foi realizada comparando as afirmações produzidas pela IA com a documentação oficial do Rust e executando os códigos apresentados.

# 5. Defeitos e correções encontrados

Durante a revisão, alguns pontos da resposta inicial da IA precisaram ser tratados com cuidado.

### 5.1. "Rust possui alta legibilidade"

Essa afirmação não pode ser comprovada por uma execução de programa, pois legibilidade é um critério de avaliação da linguagem.

**Correção:** a afirmação foi apresentada como uma avaliação baseada em características observáveis da linguagem, como sintaxe explícita, declarações e sistema de tipos, e não como uma propriedade matematicamente comprovada.

---

### 5.2. "Rust é fortemente tipada"

A expressão "fortemente tipada" pode possuir diferentes definições dependendo da bibliografia utilizada.

**Correção:** o trabalho priorizou características observáveis: Rust possui tipagem estática e não realiza conversões implícitas arbitrárias entre tipos incompatíveis.

---

### 5.3. Conversões numéricas

Foi verificado que uma atribuição direta entre tipos numéricos incompatíveis não funciona automaticamente.

Exemplo:

```rust
fn main() {
    let x: i32 = 10;
    let y: f64 = x as f64;

    println!("{}", y);
}
```

A conversão utiliza `as`, deixando explícita a operação.

---

### 5.4. Ownership

Foi necessário diferenciar **ownership** de simplesmente "gerenciamento automático de memória".

A memória é liberada automaticamente, mas isso não significa que Rust utilize garbage collection.

**ownership** é uma das regras utilizadas pelo compilador do Rust.

**Verificação:** foi consultada a documentação de ownership, movimentação e referências.

---

### 5.5. Exemplos de código

Os exemplos inicialmente produzidos pela IA foram tratados como **candidatos a teste**, e não como código automaticamente correto.

O procedimento utilizado foi:

1. Copiar o código para um arquivo `.rs` ou `.txt`;
2. Compilar utilizando `https://www.onlinegdb.com/online_rust_compiler`;
3. Corrigir eventuais erros de compilação;
4. Executar o programa;
5. Conferir a saída;
6. Somente então considerar o exemplo adequado para o trabalho.

---

# 6. Procedimento de auditoria

A auditoria seguiu três etapas:

### 1. Verificação documental

As afirmações sobre Rust foram comparadas principalmente com:

* **The Rust Programming Language (The Rust Book)**
* **Rust Reference**

### 2. Verificação prática

Os exemplos de código foram compilados e executados utilizando o GDB online:

https://www.onlinegdb.com/online_rust_compiler

Mas eles podem ser compilados usando:

```bash
rustc main.rs
```

e executados utilizando:

```bash
./main
```

No Windows:

```bash
main.exe
```


### 3. Revisão humana

Após a geração pela IA, os integrantes do grupo analisaram o conteúdo, selecionaram o que seria utilizado e verificaram os exemplos antes da versão final.

Nesta etapa, foi verificada parte das incoerências a respeito dos demais assuntos apresentados no trabalho, durante os processos de estruturação e organização.
 Parte desses problemas eram:
 - Estruturação inadequada
 - Informações irreais
 - Organização Inconsistente

# 7. Limitações do uso da IA

A IA pode produzir respostas plausíveis que contenham informações imprecisas ou simplificações excessivas. Por isso, suas respostas não foram consideradas fonte primária.

A documentação oficial do Rust foi utilizada para verificar os conceitos técnicos, enquanto os exemplos de código foram submetidos à compilação e execução.

Dessa forma, a IA foi utilizada como **ferramenta de apoio à pesquisa, organização e revisão**, enquanto a validação final do conteúdo ficou sob responsabilidade dos integrantes do grupo.
