# 🔐 Smart Wallet – Solidity Project

Este proyecto es un contrato inteligente desarrollado en Solidity que implementa una billetera inteligente con control de permisos y sistema de recuperación mediante guardianes.

## ✨ Funcionalidades principales

- **Propietario** del contrato puede:
  - Enviar ETH a cualquier dirección.
  - Autorizar a otras direcciones a enviar ETH con un límite (`allowance`).
  - Agregar o quitar *guardianes* confiables.

- **Direcciones autorizadas** pueden:
  - Enviar ETH desde el contrato hasta el límite establecido.
  - Ejecutar llamadas externas (`call`) con payload opcional.

- **Sistema de guardianes**:
  - Los guardianes pueden votar para cambiar el propietario del contrato.
  - Cuando al menos 3 guardianes votan por un nuevo propietario, el cambio se ejecuta automáticamente.

- **Recepción de fondos**:
  - El contrato acepta ETH mediante la función `receive()`.

## 🛠️ Tecnología utilizada

- Solidity `^0.8.30`
- Remix IDE (para pruebas y despliegue)
- SPDX License: MIT

## 📄 Contrato principal

Archivo: [`SmartWallet.sol`](./SmartWallet.sol)

```solidity
pragma solidity ^0.8.30;
