# Instruções para o teste frontend

Para o frontend, devemos criar uma estrutura simples, contendo:
* Header
* Menu de navegação lateral
* Tela Jogadores (listagem)
  * Botão "Adicionar jogador"
  * Tabela ou card contendo as colunas:
    * ID
    * Foto do jogador
    * Nome
    * Time que joga (nome e foto)
    * Botões de ação
* Tela Times (listagem)
  * Botão "Adicionar time"
  * Tabela ou card contendo as colunas:
    * Foto do time
    * ID
    * Nome
    * Quantidade de jogadores
    * Botões de ação
* Perfil time
  * Foto do time
  * Nome
  * Listagem de todos os jogadores em forma de card
    * Foto
    * Nome
    * Idade
* Dashboard (página inicial)
  * KPIs
    * Quantidade de times
    * Quantidade de jogadores
    * Idade média dos jogadores
  * Lista de jogadores (card)
    * Nome
    * idade
    * logo do time que joga (se tiver um time)
  * Lista de times (card)
    * Nome
    * Logo
    * Quantidade de jogadores no time 
  * Gráfico de barras de jogadores por time

Segue abaixo um layout do projeto para usar de inspiração. O layout é propositalmente simples, feito apenas para mostrar onde cada informação deve ir. A estilização não é obrigatória e não é cobrada, validaremos a aplicação apenas funcionalmente.

Requisitos funcionais:
* Dashboard
  * KPIs
  * Listagens
  * Gráficos
* Jogadores
  * Adicionar jogadore
  * Remover jogadores
  * Editar jogador
  * Listar jogadores
* Times
  * Adicionar time
  * Remover time
  * Editar time
  * Listar times
* Tratar erros com o Sweet Alert (não é necessário estilizá-lo)
* Loadings (pode usar qualquer gif/svg animado ou Skelethon) enquanto buscamos os dados no sistema todo

O propósito do teste é ser rápido e funcional, portanto:
* Não é necessário criar validações de campos complexas (apenas de campos obrigatórios)
* Não é necessário estilizar o frontend

Tecnologia/framework/biblioteca utilizada:
* Será informado via email/mensagem

---

## Layout 1 - Dashboard
Rota: /
Na home iremos ter basicamente dois componentes:
* header
* Menu de navegação lateral
* KPIs
* Listagens
* Gráficos

O **header** é um componente padrão que será utilizado em ambas as telas e será exatamente o mesmo componente.
O **menu de navegação lateral** é um componente padrão que será utilizado em ambas as telas e será exatamente o mesmo componente.
Os **KPIs** é onde colocaremos informações consolidadas sobre times e jogadores
As **listagens** é onde listaremos os jogadores e times
O **gráfico** é onde colocaremos o gráfico de jogadores por time

![image](https://github.com/user-attachments/assets/e892e259-0095-44ef-bc5f-559b0dabc9e5)

## Layout 2 - Times
Rota: `/times`

Nesta rota iremos listar todos os times e teremos:
* header
* Menu de navegação lateral
* Lista de times
* Botão "Adicionar time"
  
Nesta tela, temos 3 botões:
* Adicionar time
* Editar time
* Remover time

Ao clicar no botão de Adicionar time, é esperado que o sistema direcione para a tela de adição de time (`/times/novo`)
Ao clicar no botão de Editar time (ícone de lápis na coluna "Ações" da linha do time), direcionaremos para a tela (`/times/<id>/editar`) para editar o time da linha
Ao clicar no botão de Remover time (ícone de lixo na coluna "Ações" da linha do time), nós abriremos um Sweet Alert com a título "Tem certeza?" e a descrição "Remover o time é uma ação irreversível", com os botões "Sim" e "Não". 
  Ao clicar em "Não", cancelaremos a ação.
  Ao clicar em "Sim", removeremos o time.
  
![image](https://github.com/user-attachments/assets/cdf768fb-7741-46ad-a851-7e9a940f3f90)

OBS.: Caso o backend não retorne nenhum time, devemos escrever em tela, no lugar da tabela, a mensagem "Não existe nenhum time cadastrado"

## Layout 3 - Perfil de time
Rota: `/times/<id>`

Nesta rota iremos trazer infos do time e listar todos os jogadores daquele time, teremos:
* header
* Widget de time
* Lista de jogadores em forma de card

![image](https://github.com/user-attachments/assets/5c5d2828-f24c-4954-b28d-51af92a2f323)

## Layout 4 - Adicionar/Editar Time
Rota: `/times/novo` - Para **adicionar**

Rota: `/times/<id>/editar` - Para **editar**

A tela de adicionar time é onde teremos o formulário contendo os campos do cadastro do time, nessa tela devemos ter:
* campo "Nome" - Texto
* campo "Imagem" - Image picker
  
Ao editar, os campos já devem aparecer preenchidos ao acessar o formulário.

![image](https://github.com/user-attachments/assets/4a27e77b-2635-4f6e-91c6-6628df5caa1f)


Requisitos para a tela:
* Todos os campos são obrigatórios
* Caso dê um erro ao cadastrar o time, devemos exibir uma mensagem de erro via sweet alert
  * Título: "Erro!" 
  * Descrição: "Não conseguimos cadastrar o time, tente novamente mais tarde."
* Ao salvar, exibiremos um Sweet Alert com uma mensagem de sucesso, Titulo: "Sucesso", Descrição: "Time cadastrado com sucesso"
* Ao salvar com sucesso, retornar para a listagem de times
  * A lista deve estar atualizada

## Layout 4 - Jogadores
Rota: `/jogadores`

Nesta rota iremos listar todos os jogadores e teremos:
* header
* Menu de navegação lateral
* Lista de jogadores
* Botão "Adicionar jogador"
  
Nesta tela, temos 3 botões:
* Adicionar jogador
* Editar jogador
* Remover jogador

Ao clicar no botão de Adicionar jogador, é esperado que o sistema direcione para a tela de adição de time (`/jogadores/novo`)
Ao clicar no botão de Editar jogador (ícone de lápis na coluna "Ações" da linha do jogador), direcionaremos para a tela (`/jogadores/<id>/editar`) para editar o jogador da linha
Ao clicar no botão de Remover jogador (ícone de lixo na coluna "Ações" da linha do jogador), nós abriremos um Sweet Alert com a título "Tem certeza?" e a descrição "Remover o jogador é uma ação irreversível", com os botões "Sim" e "Não". 
  Ao clicar em "Não", cancelaremos a ação.
  Ao clicar em "Sim", removeremos o jogador.
  
![image](https://github.com/user-attachments/assets/7cc0093a-db88-4945-b213-e22661481ab7)


OBS.: Caso o backend não retorne nenhum jogador, devemos escrever em tela, no lugar da tabela, a mensagem "Não existe nenhum jogador cadastrado"

## Layout 5 - Adicionar/Editar Jogador
Rota: `/jogadores/novo` - Para **adicionar**

Rota: `/jogadores/<id>/editar` - Para **editar**
OBS.: Não teremos perfil de jogador

A tela de adicionar jogador é onde teremos o formulário contendo os campos do cadastro do jogador, nessa tela devemos ter:
* campo "Nome" - Texto
* campo "Idade" - Número inteiro
* campo "Time" - Seleção de time (apenas um time pode ser selecionado)
* campo "Imagem" - Image picker
  
Ao editar, os campos já devem aparecer preenchidos ao acessar o formulário.

![image](https://github.com/user-attachments/assets/88f6464a-6ac2-49e2-9b44-db1336e5090d)

Requisitos para a tela:
* Todos os campos são obrigatórios
* Não devemos permitir campo de texto no campo 'Idade'
* Caso dê um erro ao cadastrar o jogador, devemos exibir uma mensagem de erro via sweet alert
  * Título: "Erro!" 
  * Descrição: "Não conseguimos cadastrar o jogador, tente novamente mais tarde."
* Ao salvar, exibiremos um Sweet Alert com uma mensagem de sucesso, Titulo: "Sucesso", Descrição: "Jogador cadastrado com sucesso"
* Ao salvar com sucesso, retornar para a listagem de jogadores
  * A lista deve estar atualizada
