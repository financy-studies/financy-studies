# Documento de Requisitos do Sistema

## 1. Definição Curta

Descreva rapidamente o que é o projeto

## 2. Integrantes

* Nome completo do integrante 1
* Nome completo do integrante 2
* Nome completo do integrante 3
* Nome completo do integrante 4 

## 3. Termos e Significados

Adicione aqui, qualquer termo técnico junto de sua descrição.

## 4. Introdução

Descreva o que é projeto, sua missão, benefícios, etc.

## 5. Objetivos
Aqui você deve descrever os objetivos do trabalho indicando que o objetivo geral é desenvolver um software para solucionar o problema apresentado acima. 
- O objetivo geral deve resumir e apresentar a ideia central de um trabalho, descrevendo também a sua finalidade. 
- Os objetivos específicos darão uma maior delimitação ao tema, além de detalhar os processos necessários para a realização do trabalho.

### 6.1 Objetivo Principal
### 6.2 Objetivo Secundário

# 7. Caracteristicas do Usuário
## 7.1 Público Alvo
### 7.2 Stakeholders

Descreva aqui os stakeholders do projeto, ou seja, todos aqueles que tem interesse ou estejam envolvidos no projeto, por exemplo:
- Stakeholders internos: patrocinadores, membros de equipe, etc;
- Stakeholders externos: quem vai consumir o produto.

### 8. Personas

Crie usuários fictícios que utilizaria o sistema desenvolvido, descrevendo suas características, necessidades, etc.

# 9. Limitações

Descreva aqui TODAS as limitações que o escopo do MVP pode acabar enfrentando, desde free tier de serviços consumidos até limite de trafego suportado.

# 10. Requisitos do Sistema

Este documento apresenta duas categorias de requisitos de sistema para permitir que os clientes compreendam o que e como este produto será entregue:

**Requisitos funcionais:** os requisitos funcionais são responsáveis por gerenciar e organizar as funcionalidades presentes no sistema.

**Requisitos não funcionais:** os requisitos não funcionais são responsáveis por indicar funcionalidades que não possuem uma relação direta com as funcionalidades do projeto, mas que têm um impacto indireto em seu andamento.

Além disso, é de extrema importância compreender como funciona a sintaxe de cada requisito funcional neste projeto. A seguir, está a explicação:

**0101**

* **Primeiros dois dígitos (marcados em vermelho):** indicam o ID do módulo que será desenvolvido;
* **Últimos dois dígitos (marcados em azul):** indicam a funcionalidade que será desenvolvida.

Um exemplo de uso é o requisito de sistema **0100**, que será descrito abaixo, e que indica que o módulo de autenticação e cadastro, de ID **(01)**, conterá a funcionalidade **(00)** responsável por gerenciar os fluxos de cadastro. Isso será importante quando os desenvolvedores de software iniciarem seus trabalhos, pois permitirá identificar e categorizar mais rapidamente cada módulo e funcionalidade presentes no sistema.

## 10.1 Módulos

Liste e descreva TODOS os módulos que o sistema deve conter internamente, desde módulos de autenticação e login, até integrações em plataformas de monitoramento, como o Cloud Monitoring ou Protheus.

## 10.2 Requisitos Funcionais

| Código | Requisito Funcional | Descrição |
|--------------------|------------------------------------|----------------------------------------|
| RF0101 | Autenticação |	O sistema deve realizar o processo de autenticação |

## 10.3 Requisitos Não Funcionais

### 10.3.1 Requisitos de Padronização

| Código | Requisito de Padronização | Descrição |
|--------------------|------------------------------------|----------------------------------------|
| RNF1 | Trello |	A gestão de tarefas do projeto deve utilizar o trello |

### 10.3.2 Requisitos de Segurança

| Código | Requisito de Segurança | Descrição |
|--------------------|------------------------------------|----------------------------------------|
| RNF2 | Criptografia |	Dados considerados sensíveis, como senhas, devem ser criptografados utilizando o algoritmo Bcrypt |

### 10.3.3 Requisitos de Infraestrutura

| Código | Requisito de Infraestrutura | Descrição |
|--------------------|------------------------------------|----------------------------------------|
| RNF3 | Multi-cloud |	O sistema deve utilizar de um ambiente multi-cloud para minimizar os custos financeiros no estágio de MVP |

# 11. Arquitetura

![eb7352f8-0099-45f4-85a1-85c9cd3dfade](https://github.com/user-attachments/assets/b0b5b3ad-0f9a-44a8-9f2f-00222d3d5b30)

Coloque aqui o diagrama da infraestrutura do sistema criado juntamente com sua descrição.

# 12. Fluxos

Adicione aqui o fluxo da aplicação, por exemplo, processo de login, registro financeiro, envio de notificação, etc.

# 13. Casos de Uso

#### Gerenciar Professor (CSU01) (EXEMPLO)

Sumário: A Secretária realiza a gestão (inclusão, remoção, alteração e consulta) dos dados sobre professores.

Ator Primário: Secretária.

Ator Secundário: Coordenador.

Pré-condições: A Secretária deve ser validada pelo Sistema.

Fluxo Principal:

1) 	A Secretária requisita manutenção de professores.
2) 	O Sistema apresenta as operações que podem ser realizadas: inclusão de um novo professor, alteração de um professor, a exclusão de um professor e a consulta de dados de um professor.
3) 	A Secretária seleciona a operação desejada: Inclusão, Exclusão, Alteração ou Consulta, ou opta por finalizar o caso de uso.
4) 	Se a Secretária desejar continuar com a gestão de professores, o caso de uso retorna ao passo 2; caso contrário o caso de uso termina.

Fluxo Alternativo (3): Inclusão

a)	A Secretária requisita a inclusão de um professor. <br>
b)	O Sistema apresenta uma janela solicitando o CPF do professor a ser cadastrado. <br>
c)	A Secretária fornece o dado solicitado. <br>
d)	O Sistema verifica se o professor já está cadastrado. Se sim, o Sistema reporta o fato e volta ao início; caso contrário, apresenta um formulário em branco para que os detalhes do professor (Código, Nome, Endereço, CEP, Estado, Cidade, Bairro, Telefone, Identidade, Sexo, Fax, CPF, Data do Cadastro e Observação) sejam incluídos. <br>
e)	A Secretária fornece os detalhes do novo professor. <br>
f)	O Sistema verifica a validade dos dados. Se os dados forem válidos, inclui o novo professor e a grade listando os professores cadastrados é atualizada; caso contrário, o Sistema reporta o fato, solicita novos dados e repete a verificação. <br>

Fluxo Alternativo (3): Remoção

a)	A Secretária seleciona um professor e requisita ao Sistema que o remova. <br>
b)	Se o professor pode ser removido, o Sistema realiza a remoção; caso contrário, o Sistema reporta o fato. <br>

Fluxo Alternativo (3): Alteração

a)	A Secretária altera um ou mais dos detalhes do professor e requisita sua atualização. <br>
b)	O Sistema verifica a validade dos dados e, se eles forem válidos, altera os dados na lista de professores, caso contrário, o erro é reportado. <br>
 
Fluxo Alternativo (3): Consulta

a)	A Secretária opta por pesquisar pelo nome ou código e solicita a consulta sobre a lista de professores. <br>
b)	O Sistema apresenta uma lista professores. <br>
c)	A Secretária seleciona o professor. <br>
d)	O Sistema apresenta os detalhes do professor no formulário de professores. <br>

Pós-condições: Um professor foi inserido ou removido, seus dados foram alterados ou apresentados na tela.


# 14. ERD

![da46ca69-262d-40d9-893a-883f30a2061d](https://github.com/user-attachments/assets/2f1f4d88-ef4d-485d-87e7-0c22fb2334ba)

Adicione a estrutura de dados do sistema a ser utilizada aqui.

# 15. Custos

Adicione aqui o calculo dos custos de infraestrutura para executar o sistema

# 16. Referências
