# *Funcionamento do sistema de locadora de veículos com PHP e Bootstrap* 🔘🐘

Este documento descreve o funcionamento do sistema de locadora de veículos desenvolvido em PHP, utilizando Bootstrap para a interface, com autenticação de usuários, gerenciamento de veículos (carros e motos) e persistência de dados em arquivos JSON. O foco principal é explicar o funcionamento geral do sistema, com ênfase especial nos perfis de acesso (admin e usuário).

## 1. Visão geral do sistema

o sistema de locadora de veículos é uma aplicação web que permite:
- aurenticação de usuário com dois perfis: **admin** (administrador) e **usuário**;
- gerenciamento de veículos: cadastro, aluguel, devolução e exclusão;
- cálculo de previsão de aluguel: com base no tipo de veículo (carro ou moto) e número de dias;
- interface responsiva.

os dados são armazenados em dois arquivos JSON:
- `usuarios.json`: username, senha criptografada e perfil
- `veiculos.json`: tipo, modelo, placa e status de disponibilidade

## 2. Estrutura do sistema
O sistema utiliza:
- **PHP**: para a lógica
- **Bootstrap**: para a estilização
- **Bootstrap Icons**: para os ícones da interface
- **Composer**: para autoloading de classes
- **JSON**: para a persistência de dados

### 2.1 Componentes principais
- **Interfaces**: define a interface `Locavel` para veículos e utiliza os métodos `alugar()`, `devolver()` e `isDisponivel()`
- **Models**: classes `Veiculo` (abstrata), `Carro` e `Moto` para os veículos, com cálculo em aluguel baseado em diárias constantes (`DIARIA_CARRO` e `DIARIA_MOTO`)
- **Services**: Classes `AUTH` (autenticação e gerenciamento de usuários) e `Locadora` (gerenciamento dos veículos)
- **Views**: Template principal `template.php` para renderizar a interface e `login.php` para a autenticação
- **Controllers**: Lógica em `index.php` para processar requisições e carregar o template.
