---
description: >-
  Details the operations of our DeFi platform's main contract, managing
  investments, rebalancing, and fee structures, ensuring secure and efficient
  asset management.
---

# Fund Contract

## **Introduction**

The "Fund" contract is a central component of our DeFi platform designed to manage a portfolio of digital assets. Utilizing the Solidity programming language and deployed on the Ethereum blockchain, this contract handles the core functionalities such as asset allocation, fees management, and interactions with tokens representing fund shares.



## **Features**

* **Upgradability:** Uses UUPS (Universal Upgradeable Proxy Standard) for future-proofing and improvements without migrating assets or disrupting the existing ecosystem.
* **Security:** Implements `ReentrancyGuard` to prevent reentrant calls, enhancing transaction security.
* **Ownership Management:** Built with `Ownable` pattern allowing certain actions to be restricted to the contract owner.

## **Key Components and Functions**

### **Variables**

<table><thead><tr><th width="206">Variable</th><th width="178">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>tokens</code></td><td>Array of Structs</td><td>List of tokens managed by the fund, each containing metadata like symbol, decimals, and associated controller.</td></tr><tr><td><code>fundToken</code></td><td>Contract Interface</td><td>Represents the token that participants receive as proof of their share in the fund.</td></tr><tr><td><code>currencyToken</code></td><td>Struct</td><td>The primary currency used for transactions within the fund.</td></tr><tr><td><code>managementFee</code></td><td>uint256</td><td>Annual fee percentage for managing the assets.</td></tr><tr><td><code>performanceFee</code></td><td>uint256</td><td>Fee based on the fund's performance relative to the high water mark.</td></tr><tr><td><code>hwm</code></td><td>uint256</td><td>High Water Mark (HWM) used for calculating performance fees.</td></tr></tbody></table>

### **Functions**

<table><thead><tr><th width="207">Function Name</th><th width="151">Parameters</th><th>Description</th></tr></thead><tbody><tr><td><code>initialize</code></td><td><code>_currencyTokenAddress, _fundTokenAddress</code></td><td>Sets up the contract with initial token settings and permissions.</td></tr><tr><td><code>setStrategy</code></td><td><code>_tokenSymbols, _weights, _controllers</code></td><td>Configures the investment strategy by setting the tokens and their respective weights in the fund.</td></tr><tr><td><code>deposit</code></td><td><code>amount, receiver</code></td><td>Handles deposits by allocating the correct proportion of fund tokens to the depositor.</td></tr><tr><td><code>withdraw</code></td><td><code>shares, receiver</code></td><td>Allows withdrawals by burning the corresponding amount of fund tokens and returning the assets.</td></tr><tr><td><code>rebalance</code></td><td>None</td><td>Adjusts the fund's holdings to match the intended asset allocation strategy.</td></tr></tbody></table>



## **Security Measures**

The contract includes multiple layers of security:

* **Non-reentrancy:** To prevent re-entrancy attacks, critical functions such as `deposit` and `withdraw` are marked with the `nonReentrant` modifier.
* **Ownership Checks:** Sensitive functions are restricted to the owner, preventing unauthorized access and changes to the fund's configuration.

***



## **Conclusion**

The "Fund" contract provides a robust and flexible foundation for managing a decentralized investment fund. With built-in upgradeability and security features, it offers a scalable solution for asset management on the blockchain.
