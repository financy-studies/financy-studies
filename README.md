# Documento de Requisitos do Sistema

## 1. Definição Curta

Uma descrição sucinta do projeto: o que é, qual problema resolve e seu público-alvo. (Use 1–2 frases claras.)

**Exemplo:** `Sistema web para gerenciamento de agendamentos e pagamentos de consultórios, voltado para profissionais de saúde autônomos.`

---

## 2. Introdução

Contextualize o projeto com um parágrafo explicando a missão, visão, principais benefícios esperados e o valor agregado ao usuário final. Indique também o escopo alto (MVP) e limitações temporais, se houver.

---

## 3. Objetivos

Explique o objetivo geral do trabalho e liste objetivos específicos que detalhem as entregas e critérios de sucesso.

### 3.1 Objetivo Principal

Descreva o objetivo geral em uma frase clara.

### 3.2 Objetivos Secundários

Liste objetivos específicos que suportam o objetivo principal (ex.: integração com gateway de pagamento, API pública, relatórios mensais, etc.).

---

## 4. Termos e Significados

Inclua termos técnicos, siglas e conceitos usados no documento, com definições curtas. Isso evita ambiguidade nas especificações.

**Exemplo:**

* **MVP:** Minimum Viable Product — conjunto mínimo de funcionalidades para liberar o produto.
* **API:** Application Programming Interface — interface para comunicação entre sistemas.

---

## 5. Integrantes

Liste os membros da equipe com função/responsabilidade principal (não apenas nomes).

* **Nome completo do integrante 1** — Product Owner / Responsável pelo escopo
* **Nome completo do integrante 2** — Desenvolvedor Back-end
* **Nome completo do integrante 3** — Desenvolvedor Front-end / UI
* **Nome completo do integrante 4** — QA / DevOps

---

## 6. Características do Usuário

Descreva quem usará o sistema, suas necessidades e comportamentos. Isso orienta prioridades de UX e requisitos.

### 6.1 Público-alvo

Defina o público em termos demográficos, nível técnico e contexto de uso (ex.: profissionais liberais, administradores, pacientes, etc.).

### 6.2 Stakeholders

Liste partes interessadas internas e externas e suas expectativas principais.

* **Stakeholders internos:** patrocinadores, equipe de desenvolvimento, suporte.
* **Stakeholders externos:** clientes finais, parceiros de integração, provedores de pagamento.

### 6.3 Personas

Crie 2–3 personas fictícias com nome, papel, objetivos e principais frustrações para guiar decisões de produto.

**Exemplo:**

* *Maria — Clínica privada* — precisa de agendamento rápido e relatórios mensais; frustração: duplicidade de atendimentos.

---

## 7. Limitações

Documento de todas as limitações conhecidas do MVP: restrições técnicas, orçamentárias, de terceiros (free tiers), limites de tráfego previstos, dependências externas e requisitos regulatórios.

**Exemplo:** limite de 10.000 requisições/mês na camada gratuita do provedor X; integração com gateway disponível apenas via API versão Y.

---

## 8. Requisitos do Sistema

### 8.1 Módulos

Liste e descreva os módulos do sistema — cada item deve ter um nome, propósito e breve descrição de responsabilidades.

**Exemplo de módulos:**

* **Autenticação e Cadastro:** fluxos de login, cadastro, recuperação de senha e validação de conta.
* **Gerenciamento de Usuários:** CRUD de perfis e permissões.
* **Faturamento e Assinaturas:** criação de carteiras, cobranças recorrentes, integração com gateway.
* **Monitoramento:** telemetria e alertas (Cloud Monitoring / Prometheus).

### 8.2 Requisitos Funcionais

Liste os requisitos funcionais com código, título e descrição clara.

| Código | Requisito Funcional | Descrição                                                                                           |
| ------ | ------------------- | --------------------------------------------------------------------------------------------------- |
| RF01   | Autenticação        | O sistema deve realizar o processo de autenticação (login/logout) com validação por email e tokens. |

> Dica: adote um padrão de codificação (ex.: `RFxx`, `RF-0100`) e mantenha uma breve regra de numeração.

### 8.3 Requisitos Não Funcionais

Divida em categorias: padronização, segurança, infraestrutura, performance, disponibilidade etc. Inclua código e descrição.

#### 8.3.1 Requisitos de Padronização

| Código | Requisito de Padronização | Descrição                                                                       |
| ------ | ------------------------- | ------------------------------------------------------------------------------- |
| RNF1   | Gestão de Tarefas         | A gestão de tarefas do projeto deve utilizar o Trello (ou ferramenta definida). |

#### 8.3.2 Requisitos de Segurança

| Código | Requisito de Segurança | Descrição                                                                                   |
| ------ | ---------------------- | ------------------------------------------------------------------------------------------- |
| RNF2   | Criptografia           | Dados sensíveis (senhas, tokens) devem ser armazenados criptografados com algoritmo Bcrypt. |

#### 8.3.3 Requisitos de Infraestrutura

| Código | Requisito de Infraestrutura | Descrição                                                                                     |
| ------ | --------------------------- | --------------------------------------------------------------------------------------------- |
| RNF3   | Multi-cloud                 | O sistema deve contemplar estratégia multi-cloud para reduzir risco e otimizar custos no MVP. |

---

## 9. Arquitetura

Insira o diagrama da infraestrutura e uma descrição resumida dos componentes: serviços, bancos, filas, integrações externas e responsabilidades de cada bloco.

![Diagrama de Arquitetura](https://github.com/user-attachments/assets/b0b5b3ad-0f9a-44a8-9f2f-00222d3d5b30)

> Explique aqui: por exemplo, onde o load balancer fica, quais serviços são stateless, qual banco é primário, estratégia de backups, etc.

---

## 10. Modelo de Dados (ERD)

Inclua o diagrama de entidade-relacionamento e uma descrição das tabelas/entidades principais, chaves, índices e restrições importantes.

![ERD](https://github.com/user-attachments/assets/2f1f4d88-ef4d-485d-87e7-0c22fb2334ba)

> Observação: documente também políticas de versionamento do schema e scripts de migração esperados.

---

## 11. Fluxos

Descreva os fluxos principais da aplicação (ex.: processo de login, cadastro, registro financeiro, envio de notificações). Para cada fluxo, inclua pré-condições, etapas e pós-condições.

**Exemplo (Login):**

* **Pré-condição:** usuário cadastrado e ativo.
* **Fluxo:** 1) Usuário insere credenciais → 2) Sistema valida → 3) Retorna token de sessão.
* **Pós-condição:** sessão criada e token com validade configurada.

---

## 12. Casos de Uso

Documente casos de uso relevantes com sumário, atores, pré-condições, fluxo principal, fluxos alternativos e pós-condições.

#### Exemplo — Gerenciar Professor (CSU01)

* **Sumário:** A Secretária gerencia (incluir, remover, alterar, consultar) dados de professores.
* **Ator Primário:** Secretária.
* **Ator Secundário:** Coordenador.
* **Pré-condição:** Secretária autenticada e autorizada.

**Fluxo Principal:**

1. A Secretária requisita manutenção de professores.
2. O sistema apresenta as operações disponíveis (inclusão, alteração, exclusão, consulta).
3. A Secretária seleciona a operação e segue o fluxo correspondente.

**Fluxos Alternativos:**

* Inclusão: validação de CPF, preenchimento de formulário, persistência.
* Remoção: validação de restrições antes de excluir.
* Alteração/Consulta: validação dos dados e confirmação.

**Pós-condição:** Dados do professor atualizados conforme operação.

---

## 13. Custos

Apresente o cálculo estimado dos custos de infraestrutura e serviços (por mês e por 12 meses): hosting, banco, filas, balanceamento, contratos de terceiros, licenças e custos de suporte.

> Inclua premissas (número de usuários, requisições/mês, retenção de dados) e como cada premissa impacta o custo.

---

## 14. Referências

Liste documentos, APIs, padrões, normas e links utilizados como base para este documento. Inclua versão e data quando aplicável.
