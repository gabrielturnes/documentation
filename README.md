Gabriel Farias Turnes
### Reservas de Lanches - IFSC/SJ

## 1. Declara��o de necessidade

Tendo em vista que brevemente o IFSC de S�o Jos� ir� auxiliar os alunos necessitados do per�odo noturno com a doa��o de lanches da cantina, � necess�rio uma administra��o e gerenciamento do fornecimento dessa merenda para que n�o haja desperd�cio.

Por isso, o IFSC sentiu a necessidade de criar uma aplica��o para automatizar e facilitar a organiza��o da distribui��o dos alimentos.

  

## 2. Viabilidade

O sistema se torna vi�vel pois n�o se trata de um projeto complexo para os desenvolvedores e n�o ter� custos para a Institui��o Federal de Santa Catarina, pois ser� desenvolvido pelos alunos de Programa��o Orientada � Objeto.

O projeto n�o � complexo, porque ser� desenvolvido na linguagem JAVA, que vem sendo usada durante todo o semestre e ser� rodado em sistemas com Android (Open-Source).

## 3. Declara��o do escopo do sistema

O aplicativo permitir� que os usu�rios (alunos autorizados) fa�am pedidos de lanches pelo sistema e que os administradores (servidores IFSC) controlem esses pedidos e usu�rios.

## 4. Lista de interessados que participaram do levantamento de requisitos


| | |
|--|--|
| Saul Oliveira |Cliente  |
| Gabriel Farias Turnes |Aluno de Programa��o Orientada a Objeto  |









## 5. Descri��o do ambiente t�cnico do sistema

O aplicativo ser� desenvolvido para um sistema Android. Essas informa��es s�o transferidas para um banco de dados e a partir de relat�rios os dados dos alunos ser�o tratados de acordo com as inten��es do usu�rio. O tratamento ser� feito a partir de um sistema implementado na linguagem Java.

## 6. Lista de requisitos

### 6.1 Funcionais

**RF1**. Permitir que o aluno reserve seu lanche.

**RF2**. Permitir que o aluno possa cancelar a reserva do seu lanche.

**RF3**. Permitir que o aluno possa ver o card�pio da semana.

**RF4**. Permitir que o aluno possa ver todos os pedidos j� feitos.

**RF5**. Permitir que o aluno visualize o QRCode da merenda do dia.

### 6.2 N�o funcionais

**RNF1**. O sistema deve possuir uma interface simples e direta.

**RNF2**. O sistema deve se conectar com um banco de dados que estar� armazenado os alunos autorizados.

**RNF3**. O sistema deve se conectar com um banco de dados que estar� armazenado os card�pios do dia.

**RNF4**. O sistema deve se conectar com um banco de dados que estar� armazenado os tickets de cada pedido.

  
  

## 7. Regras de neg�cio
|   | Pedido de lanche (RN01)|
|--|--|
| Descri��o | O sistema permitir� que o aluno reserve um lanche 4 dias antes at� as 21 horas do dia anterior e que j� n�o tenha feito a reserva desse dia. |


|  |Cancelamento de pedido (RN02)  |
|--|--|
| Descri��o | O sistema permitir� que o aluno cancele uma reserva at� as 21 horas do dia anterior. |

|  | Autentica��o do Usu�rio (RN03) |
|--|--|
|  Descri��o| O aluno s� ser� autenticado se estiver cadastrado e com permiss�o para acessar o sistema. |
  
  
 
  
|  |Visualizar QRCode (RN04)  |
|--|--|
|  Descri��o| O aluno s� poder� visualizar o QRCode de seu pedido apenas no mesmo dia da retirada do lanche.
 |







  

## 8. Casos de Uso

### Autentica��o do aplicativo (CSU01)

**Ator prim�rio**: Aluno.

**Ator secund�rio**: Banco de dados com as informa��es do aluno.

**Resumo**: O usu�rio coloca o usu�rio e a senha do sistema.

**Fluxo Principal:**

 1. O aluno abre o aplicativo.
 2. O aplicativo abre a tela com dois campos para preenchimento, o usu�rio e a senha.
 3. O aluno preenche ambos os campos com seus dados.
 4. O sistema faz uma verifica��o com o banco de dados para ver se os dados est�o corretos.
 5. � exibido a tela com o menu do sistema.

Exce��es:

1.  O aluno inseriu os dados incorretamente. (CSU02).
    

### Erro ao autenticar-se (CSU02)

**Ator prim�rio**: Usu�rio.

**Ator secund�rio**: Banco de dados com as informa��es do aluno.

**Resumo**: O usu�rio erra os dados.

**Fluxo Principal**:

 1. O aluno abre o aplicativo.
 2. O aplicativo abre a tela com dois campos para preenchimento, o usu�rio e a senha.
 3. O aluno preenche ambos os campos com seus dados.
 4. O sistema faz uma verifica��o com o banco de dados para ver se os dados est�o corretos.
 5. � exibido a tela com o menu do sistema.
 6. O sistema n�o localiza os dados informados no banco de dados.
 7. O aplicativo retorna a tela de login exibindo uma mensagem de erro.
 8. Retorna ao passo 3 at� que o aluno se autentique.

### Realizar pedido do lanche (CSU03)

**Ator prim�rio**: Aluno.

**Ator secund�rio**: Banco de dados com as informa��es dos lanches.

**Pr�-condi��o**: O aluno estar logado no sistema (ver CSU01).

**Resumo**: O aluno faz o pedido do lanche no dia desejado.

 1. O aluno seleciona no menu a op��o de pedir lanche.
 2. � aberta a tela com as datas para o aluno pedir o lanche.
 3.  O aluno seleciona a data que deseja reservar o lanche.
 4. O aluno confirma a reserva do lanche para a data selecionada.
 5. O sistema cria um ticket para o pedido de lanche e armazena no banco de dados.
 
Exce��es:
1.  O aluno seleciona uma data inv�lida. (CSU04)
    

  
  

### Erro ao pedir lanche (CSU04)

**Ator prim�rio:** Aluno.

**Pr�-condi��o**: O aluno estar logado no sistema (ver CSU01).

**Resumo**: O aluno faz o pedido do lanche em um dia inv�lido.

 1. O aluno seleciona no menu a op��o de pedir lanche.
 2. � aberta a tela com as datas para o aluno pedir o lanche.
 3. O aluno seleciona a data que deseja reservar o lanche, por�m ela � inv�lida.
 4. O aluno confirma a reserva do lanche para a data selecionada.
 5. O sistema exibe um erro na tela e retorna para a etapa 2.

  
  

### Cancelar lanche (CSU05)

**Ator prim�rio**: Aluno.

**Ator secund�rio**: Banco de dados com as informa��es dos lanches.

**Pr�-condi��o**: O aluno deve ter feito um pedido (ver CSU03).

**Resumo**: O aluno faz o cancelamento de uma reserva.

 1. O aluno seleciona no menu a op��o de cancelar lanche.
 2. � aberta a tela com os lanches que j� foram pedidos.
 3. O aluno seleciona o lanche que deseja cancelar.
 4. O aluno confirma o cancelamento da reserva do lanche para a data selecionada.
 5. O sistema exclui a reserva do banco de dados.

Exce��es:

1.  O aluno tenta cancelar o pedido depois das 21 horas do dia anterior. (CSU06)
    

  

### Erro ao cancelar lanche (CSU06)

**Ator prim�rio**: Aluno.

**Pr�-condi��o**: O aluno deve ter feito um pedido (ver CSU03).

**Resumo**: O aluno faz o cancelamento de uma reserva.

 1. O aluno seleciona no menu a op��o de cancelar lanche.
 2. � aberta a tela com os lanches que j� foram pedidos.
 3. O aluno seleciona o lanche que deseja cancelar.
 4. O aluno confirma o cancelamento da reserva do lanche para a data selecionada.
 5. O sistema exibe uma mensagem de erro e retorna para a etapa 2.

### Exibir QRCode (CSU06)

**Ator prim�rio**: Aluno.

**Ator secund�rio**: Banco de dados com as informa��es dos lanches.

**Pr�-condi��o**: O aluno deve ter feito um pedido para esse dia (ver CSU03).

**Resumo**: O aplicativo exibe na tela o QRCode do pedido.

 1. O aluno seleciona no menu a op��o de exibir pedido do dia.
 2. � aberta a tela com o QRCode do pedido.

  

### Exibir Card�pio (CSU07)

**Ator prim�rio**: Aluno.

**Ator secund�rio**: Banco de dados com as informa��es dos lanches.

**Resumo**: O aplicativo exibe na tela o card�pio dos dias.

 1. O aluno seleciona no menu a op��o de exibir card�pio.
 2. � aberta a tela com o card�pio.
 
## 9. Telas do aplicativo

### Login
### Menu
### Cardapio
### QRCode
### Reservar Lanche
### Cancelar Lanche