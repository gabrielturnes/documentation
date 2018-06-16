Gabriel Farias Turnes
### Reservas de Lanches - IFSC/SJ

## 1. Declaração de necessidade

Tendo em vista que brevemente o IFSC de São José irá auxiliar os alunos necessitados do período noturno com a doação de lanches da cantina, é necessário uma administração e gerenciamento do fornecimento dessa merenda para que não haja desperdício.

Por isso, o IFSC sentiu a necessidade de criar uma aplicação para automatizar e facilitar a organização da distribuição dos alimentos.

  

## 2. Viabilidade

O sistema se torna viável pois não se trata de um projeto complexo para os desenvolvedores e não terá custos para a Instituição Federal de Santa Catarina, pois será desenvolvido pelos alunos de Programação Orientada à Objeto.

O projeto não é complexo, porque será desenvolvido na linguagem JAVA, que vem sendo usada durante todo o semestre e será rodado em sistemas com Android (Open-Source).

## 3. Declaração do escopo do sistema

O aplicativo permitirá que os usuários (alunos autorizados) façam pedidos de lanches pelo sistema e que os administradores (servidores IFSC) controlem esses pedidos e usuários.

## 4. Lista de interessados que participaram do levantamento de requisitos


| | |
|--|--|
| Saul Oliveira |Cliente  |
| Gabriel Farias Turnes |Aluno de Programação Orientada a Objeto  |









## 5. Descrição do ambiente técnico do sistema

O aplicativo será desenvolvido para um sistema Android. Essas informações são transferidas para um banco de dados e a partir de relatórios os dados dos alunos serão tratados de acordo com as intenções do usuário. O tratamento será feito a partir de um sistema implementado na linguagem Java.

## 6. Lista de requisitos

### 6.1 Funcionais

**RF1**. Permitir que o aluno reserve seu lanche.

**RF2**. Permitir que o aluno possa cancelar a reserva do seu lanche.

**RF3**. Permitir que o aluno possa ver o cardápio da semana.

**RF4**. Permitir que o aluno possa ver todos os pedidos já feitos.

**RF5**. Permitir que o aluno visualize o QRCode da merenda do dia.

### 6.2 Não funcionais

**RNF1**. O sistema deve possuir uma interface simples e direta.

**RNF2**. O sistema deve se conectar com um banco de dados que estará armazenado os alunos autorizados.

**RNF3**. O sistema deve se conectar com um banco de dados que estará armazenado os cardápios do dia.

**RNF4**. O sistema deve se conectar com um banco de dados que estará armazenado os tickets de cada pedido.

  
  

## 7. Regras de negócio
|   | Pedido de lanche (RN01)|
|--|--|
| Descrição | O sistema permitirá que o aluno reserve um lanche 4 dias antes até as 21 horas do dia anterior e que já não tenha feito a reserva desse dia. |


|  |Cancelamento de pedido (RN02)  |
|--|--|
| Descrição | O sistema permitirá que o aluno cancele uma reserva até as 21 horas do dia anterior. |

|  | Autenticação do Usuário (RN03) |
|--|--|
|  Descrição| O aluno só será autenticado se estiver cadastrado e com permissão para acessar o sistema. |
  
  
 
  
|  |Visualizar QRCode (RN04)  |
|--|--|
|  Descrição| O aluno só poderá visualizar o QRCode de seu pedido apenas no mesmo dia da retirada do lanche.
 |







  

## 8. Casos de Uso

### Autenticação do aplicativo (CSU01)

**Ator primário**: Aluno.

**Ator secundário**: Banco de dados com as informações do aluno.

**Resumo**: O usuário coloca o usuário e a senha do sistema.

**Fluxo Principal:**

 1. O aluno abre o aplicativo.
 2. O aplicativo abre a tela com dois campos para preenchimento, o usuário e a senha.
 3. O aluno preenche ambos os campos com seus dados.
 4. O sistema faz uma verificação com o banco de dados para ver se os dados estão corretos.
 5. É exibido a tela com o menu do sistema.

Exceções:

1.  O aluno inseriu os dados incorretamente. (CSU02).
    

### Erro ao autenticar-se (CSU02)

**Ator primário**: Usuário.

**Ator secundário**: Banco de dados com as informações do aluno.

**Resumo**: O usuário erra os dados.

**Fluxo Principal**:

 1. O aluno abre o aplicativo.
 2. O aplicativo abre a tela com dois campos para preenchimento, o usuário e a senha.
 3. O aluno preenche ambos os campos com seus dados.
 4. O sistema faz uma verificação com o banco de dados para ver se os dados estão corretos.
 5. É exibido a tela com o menu do sistema.
 6. O sistema não localiza os dados informados no banco de dados.
 7. O aplicativo retorna a tela de login exibindo uma mensagem de erro.
 8. Retorna ao passo 3 até que o aluno se autentique.

### Realizar pedido do lanche (CSU03)

**Ator primário**: Aluno.

**Ator secundário**: Banco de dados com as informações dos lanches.

**Pré-condição**: O aluno estar logado no sistema (ver CSU01).

**Resumo**: O aluno faz o pedido do lanche no dia desejado.

 1. O aluno seleciona no menu a opção de pedir lanche.
 2. É aberta a tela com as datas para o aluno pedir o lanche.
 3.  O aluno seleciona a data que deseja reservar o lanche.
 4. O aluno confirma a reserva do lanche para a data selecionada.
 5. O sistema cria um ticket para o pedido de lanche e armazena no banco de dados.
 
Exceções:
1.  O aluno seleciona uma data inválida. (CSU04)
    

  
  

### Erro ao pedir lanche (CSU04)

**Ator primário:** Aluno.

**Pré-condição**: O aluno estar logado no sistema (ver CSU01).

**Resumo**: O aluno faz o pedido do lanche em um dia inválido.

 1. O aluno seleciona no menu a opção de pedir lanche.
 2. É aberta a tela com as datas para o aluno pedir o lanche.
 3. O aluno seleciona a data que deseja reservar o lanche, porém ela é inválida.
 4. O aluno confirma a reserva do lanche para a data selecionada.
 5. O sistema exibe um erro na tela e retorna para a etapa 2.

  
  

### Cancelar lanche (CSU05)

**Ator primário**: Aluno.

**Ator secundário**: Banco de dados com as informações dos lanches.

**Pré-condição**: O aluno deve ter feito um pedido (ver CSU03).

**Resumo**: O aluno faz o cancelamento de uma reserva.

 1. O aluno seleciona no menu a opção de cancelar lanche.
 2. É aberta a tela com os lanches que já foram pedidos.
 3. O aluno seleciona o lanche que deseja cancelar.
 4. O aluno confirma o cancelamento da reserva do lanche para a data selecionada.
 5. O sistema exclui a reserva do banco de dados.

Exceções:

1.  O aluno tenta cancelar o pedido depois das 21 horas do dia anterior. (CSU06)
    

  

### Erro ao cancelar lanche (CSU06)

**Ator primário**: Aluno.

**Pré-condição**: O aluno deve ter feito um pedido (ver CSU03).

**Resumo**: O aluno faz o cancelamento de uma reserva.

 1. O aluno seleciona no menu a opção de cancelar lanche.
 2. É aberta a tela com os lanches que já foram pedidos.
 3. O aluno seleciona o lanche que deseja cancelar.
 4. O aluno confirma o cancelamento da reserva do lanche para a data selecionada.
 5. O sistema exibe uma mensagem de erro e retorna para a etapa 2.

### Exibir QRCode (CSU06)

**Ator primário**: Aluno.

**Ator secundário**: Banco de dados com as informações dos lanches.

**Pré-condição**: O aluno deve ter feito um pedido para esse dia (ver CSU03).

**Resumo**: O aplicativo exibe na tela o QRCode do pedido.

 1. O aluno seleciona no menu a opção de exibir pedido do dia.
 2. É aberta a tela com o QRCode do pedido.

  

### Exibir Cardápio (CSU07)

**Ator primário**: Aluno.

**Ator secundário**: Banco de dados com as informações dos lanches.

**Resumo**: O aplicativo exibe na tela o cardápio dos dias.

 1. O aluno seleciona no menu a opção de exibir cardápio.
 2. É aberta a tela com o cardápio.
 
## 9. Telas do aplicativo

### Login
### Menu
### Cardapio
### QRCode
### Reservar Lanche
### Cancelar Lanche