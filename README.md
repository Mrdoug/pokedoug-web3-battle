# PokeDoug - Pokémon NFT Battle Game

PokeDoug é um jogo de batalha de Pokémon baseado em NFTs, construído em Solidity e que segue o padrão ERC-721. Cada Pokémon é único e pode batalhar para aumentar seu nível. Apenas o dono do jogo pode criar novos Pokémons, mas os jogadores que possuem seus próprios NFTs podem batalhar uns com os outros para evoluir seus Pokémons.

## Sumário
- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Pré-requisitos](#pré-requisitos)
- [Instalação](#instalação)
- [Uso](#uso)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Sobre o Projeto

O PokeDoug é um jogo que utiliza a tecnologia de tokens não fungíveis (NFTs) para representar Pokémons digitais exclusivos. Cada Pokémon é único, com seu próprio nome, nível e imagem. Os jogadores podem batalhar entre si para melhorar o nível de seus Pokémons.

Este projeto foi desenvolvido com fins educacionais para aprender sobre contratos inteligentes, NFTs, e jogos descentralizados utilizando Solidity.

## Funcionalidades

- **Criar Pokémons**: Apenas o dono do contrato (gameOwner) pode criar novos Pokémons com nome e imagem personalizados.
- **Batalhas de Pokémons**: Proprietários de Pokémons podem batalhar com outros Pokémons para ganhar experiência e aumentar de nível.
- **Transferência de NFTs**: Como o contrato segue o padrão ERC-721, os Pokémons podem ser transferidos entre endereços como qualquer outro NFT.

## Pré-requisitos

- Node.js
- NPM ou Yarn
- Solidity ^0.8.0
- OpenZeppelin Contracts

## Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/pokedoug.git
    ```
   
2. Navegue até o diretório do projeto:
    ```bash
    cd pokedoug
    ```

3. Instale as dependências necessárias:
    ```bash
    npm install
    # ou
    yarn install
    ```

4. Certifique-se de ter as bibliotecas do OpenZeppelin para contratos ERC-721:
    ```bash
    npm install @openzeppelin/contracts
    # ou
    yarn add @openzeppelin/contracts
    ```

## Uso

1. **Deploy do Contrato**:
    Faça o deploy do contrato `PokeDoug.sol` em uma rede Ethereum (pode ser uma rede de testes usando o remix ide. para gerar as carteiras e blockchain usei o ganache rodando localmente).

2. **Criar Pokémons**:
    Apenas o endereço `gameOwner` (o endereço que fez o deploy do contrato) pode chamar a função `createNewPokemon` para criar um novo Pokémon:
    ```solidity
    function createNewPokemon(string memory _name, address _to, string memory _img)
    ```

3. **Batalhar com Pokémons**:
    Qualquer jogador que possua um Pokémon pode iniciar uma batalha com outro Pokémon:
    ```solidity
    function battle(uint _attackingPokemon, uint _defendingPokemon)
    ```
    - O Pokémon atacante ganha 2 níveis se tiver um nível maior ou igual ao do defensor. Caso contrário, ele ganha 1 nível, e o defensor ganha 2.

4. **Transferir Pokémons**:
    Como o contrato segue o padrão ERC-721, os Pokémons podem ser transferidos entre endereços.
