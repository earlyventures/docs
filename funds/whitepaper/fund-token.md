---
description: >-
  Details our ERC20 token representing shares in the fund, offering tradability
  and governance rights to investors.
---

# Fund Token

## **Introduction**

In our DeFi ecosystem, the "Fund Token" contract serves as the cornerstone for representing ownership shares within the fund. Each token issued by this contract embodies a stake in the underlying assets of the fund, mirroring their performance and value fluctuations. This alignment ensures that the token's market value is a direct reflection of the total asset value held by the fund.

## **Features**

* **ERC20 Standard:** Adheres to the widely-adopted ERC20 standard, facilitating broad compatibility with wallets and exchanges.
* **Tradability:** Tokens can be freely traded on the open market, offering liquidity and easy access for investors.
* **Governance Rights:** Implements `ERC20Votes`, providing token holders with voting rights that may be used in fund governance or other decision-making processes.

## **Contract Functions**

### **Key Methods**

| Method Name | Parameters       | Description                                                         |
| ----------- | ---------------- | ------------------------------------------------------------------- |
| `mint`      | `account, value` | Mints new tokens to an account, increasing the total supply.        |
| `burn`      | `account, value` | Burns tokens from an account, decreasing the total supply.          |
| `decimals`  | None             | Returns the number of decimals used to get its user representation. |

## **Governance Features**

The token extends `ERC20Votes`, which integrates governance capabilities, allowing token holders to participate in key decisions based on their stake. This feature enhances the democratic aspect of the fund, aligning investor interests with fund management.

## **Security Measures**

* **Ownership Controls:** Only the contract owner can mint or burn tokens, ensuring that token supply adjustments are governed by strict controls.
* **Interface Compliance:** Supports ERC-165 to declare the interfaces it implements, including `IVotes`, enabling interaction with governance protocols.

***



## **Conclusion**

The "Fund Token" contract is an integral part of our investment platform, providing a liquid, tradable representation of fund shares that not only reflects the value of the underlying assets but also empowers investors through governance rights. This setup aligns with our commitment to transparency and investor control in the fund management process.
