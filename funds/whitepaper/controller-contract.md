---
description: >-
  Details the management of liquidity and synthetic assets within the fund,
  ensuring dynamic pricing and secure transactions.
---

# Controller Contract



## **Introduction**

The "Controller" contract plays a pivotal role in our DeFi platform by managing the liquidity and asset control within the fund. It interfaces with synthetic assets and orchestrates their dynamics to maintain fund stability and responsiveness to market conditions.

## **Features**

* **Role-Based Access Control:** Implements `AccessControlEnumerableUpgradeable` to manage permissions across different operational roles such as fund managers and APIs.
* **Upgradable:** Built with `UUPSUpgradeable` to ensure that the contract can evolve with minimal disruption.
* **Asset Management:** Manages synthetic tokens, controlling their issuance, pricing, and exchange.

## **Key Components and Functions**

### **Functions**

| Function Name       | Parameters                            | Description                                                           |
| ------------------- | ------------------------------------- | --------------------------------------------------------------------- |
| `addSyntheticToken` | `base, token`                         | Registers a new synthetic asset within the fund.                      |
| `setFee`            | `_fee`                                | Adjusts the transaction fee for buying and selling synthetic tokens.  |
| `buy`               | `base, symbol, baseAmount, receiver`  | Facilitates the purchase of synthetic tokens using the base currency. |
| `sell`              | `base, symbol, tokenAmount, receiver` | Allows the sale of synthetic tokens back to the base currency.        |
| `setTokenPrice`     | `base, symbol, price`                 | Sets or updates the market price of a synthetic token.                |

### **Events**

| Event Name            | Parameters            | Description                                                    |
| --------------------- | --------------------- | -------------------------------------------------------------- |
| `FeeUpdated`          | `newFee`              | Emitted when the transaction fee is updated.                   |
| `SyntheticTokenAdded` | `base, symbol, token` | Announced when a new synthetic token is added to the platform. |

## **Use Cases**

### **Liquidity Provision:**

* The controller contract is essential for providing liquidity to the fund by enabling the seamless exchange of synthetic assets.

### **Dynamic Pricing:**

* It adjusts synthetic asset prices in real-time, ensuring that the fund's valuation reflects current market conditions.

## **Fee Management:**

* Oversees the implementation of fees for transactions within the fund, which are crucial for operational sustainability.

## **Security Measures**

* **Access Restrictions:** Utilizes role-based permissions to restrict sensitive functions to authorized operators only, preventing unauthorized access and ensuring integrity.
* **Safe Transfers:** Leverages `SafeERC20` for secure token transfers, mitigating risks associated with token transactions.

***



## **Conclusion**

The "Controller" contract is integral to the fund's ability to manage its synthetic assets effectively. It supports a dynamic and responsive investment environment, ensuring that the fund remains competitive and adaptable to market changes. This contract fosters a controlled and secure ecosystem for asset management on the blockchain.
