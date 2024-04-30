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

<table><thead><tr><th width="207">Function Name</th><th width="253">Parameters</th><th>Description</th></tr></thead><tbody><tr><td><code>initialize</code></td><td><code>_currencyTokenAddress, _fundTokenAddress</code></td><td>Sets up the contract with initial token settings and permissions.</td></tr><tr><td><code>setStrategy</code></td><td><code>_tokenSymbols, _weights, _controllers</code></td><td>Configures the investment strategy by setting the tokens and their respective weights in the fund.</td></tr><tr><td><code>deposit</code></td><td><code>amount, receiver</code></td><td>Handles deposits by allocating the correct proportion of fund tokens to the depositor.</td></tr><tr><td><code>withdraw</code></td><td><code>shares, receiver</code></td><td>Allows withdrawals by burning the corresponding amount of fund tokens and returning the assets.</td></tr><tr><td><code>rebalance</code></td><td>None</td><td>Adjusts the fund's holdings to match the intended asset allocation strategy.</td></tr></tbody></table>

## **Use Cases**

### **Investor :**

* Investors can deposit currency into the fund in exchange for fund shares. This process involves the fund's strategy to allocate the deposited assets among various tokens according to predefined weights.



### **Fee Collection:**

* The contract periodically calculates and collects management and performance fees based on the fund's rules. These fees are taken from the fund's assets and converted to the primary currency token.

### **Rebalancing Portfolio:**

* To ensure the fund's asset allocation remains aligned with the strategic targets, the fund periodically rebalances its portfolio. This might involve selling assets that exceed their target allocation and buying those underrepresented.
* The launch date of Earlyventures Crypto100 ETF Index is 2024-05-01 08:00 UTC. The first rebalance is scheduled for shortly after launch.

#### **Regular Rebalances**

The Index constituents and their weights will be automatically rebalanced every Sunday at 00:00:00 UTC to adapt to changes in the market and to reflect the respective fluctuations of each constituent’s market capitalization. For more details about weight rebalancing, please refer to the earlier section on asset weight management.

#### **Special Adjustments**

Special adjustments are deemed necessary when one or several constituents face drastic changes (e.g., delisting or lack of organic volume). Earlyventures will keep users informed of future Index adjustments. Two kinds of special adjustments can occur:

* Exclusion of an existing constituent and recalculation of the weights (and divisors) for the remaining constituents; or
* Exclusion of an existing constituent and replacement with a different asset listed on the Earlyventures market, where recalculation would also be needed, causing the index to be rebalanced as well.

#### **Hard Fork/Airdrop/Mapping Adjustment**

The Earlyventures Crypto100 Index, which is based on blockchain-based assets, will be adjusted for blockchain-specific events affecting one or several constituents, such as a hard fork/airdrop/mapping, in accordance with these guidelines:

* No adjustments are needed for soft forks or hard forks that do not generate new tokens;
* For hard forks/airdrops that create a new token, the new token should be included in the Index with the same weighting as was given to the original token and excluded on the next regular rebalance if sample selection criteria are not met; and
* For airdrops/mappings that lead to a token being replaced by new tokens, especially for split/reverse split occasions, the existing token should be replaced by the new token(s) with the weight adjusted according to the split ratio.

## **Security Measures**

The contract includes multiple layers of security:

* **Non-reentrancy:** To prevent re-entrancy attacks, critical functions such as `deposit` and `withdraw` are marked with the `nonReentrant` modifier.
* **Ownership Checks:** Sensitive functions are restricted to the owner, preventing unauthorized access and changes to the fund's configuration.

## **Conclusion**

The "Fund" contract provides a robust and flexible foundation for managing a decentralized investment fund. With built-in upgradeability and security features, it offers a scalable solution for asset management on the blockchain.
