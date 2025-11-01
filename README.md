🚀 HelloArchitect — смарт-контракт, задеплоенный в тестовой сети Arc

Этот проект показывает, как развернуть простой контракт в Arc Testnet с помощью Foundry и GitHub Actions (без установки локальных инструментов).

🧱 Контракт

Файл: src/HelloArchitect.sol

Контракт возвращает и изменяет приветствие.

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.30;

contract HelloArchitect {
    string private greeting = "Hello Architect!";

    event GreetingChanged(string newGreeting);

    function getGreeting() public view returns (string memory) {
        return greeting;
    }

    function setGreeting(string memory newGreeting) public {
        greeting = newGreeting;
        emit GreetingChanged(newGreeting);
    }
}

🌐 Деплой

✅ Контракт задеплоен в Arc Testnet

Deployer: 0x8E3A079D4e48d8aC485c669367Ee6d60E4bF2dA6

Contract address: 0xF44789647F8FE0a27487b26eb92E4f3E1334487C

Transaction hash: 0xfe4da8f10c5cb4e39c29772ae8c73a68068a303cb478d95f113039568f166efc

⚙️ Автоматический деплой через GitHub Actions

Файл workflow: .github/workflows/deploy.yml

uses: foundry-rs/foundry-toolchain@v1
with:
  version: stable


Deployment запускается вручную во вкладке Actions → Run workflow.

🧪 Как повторить

Создай репозиторий и добавь контракт в src/HelloArchitect.sol

Создай секреты:

PRIVATE_KEY — приватный ключ кошелька с тестовыми токенами Arc

ARC_TESTNET_RPC_URL — RPC-ссылка на Arc testnet

Добавь .github/workflows/deploy.yml

Запусти деплой во вкладке Actions

📖 Полезные ссылки

🌐 Arc Docs — Deploy on Arc

💧 Arc Faucet

🔍 Arc Explorer
