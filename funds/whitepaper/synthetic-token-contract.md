---
description: >-
  Details How synthetic tokens bridge asset availability gaps on the Polygon
  blockchain, ensuring liquidity and real-time asset backing.
---

# Synthetic Token Contract

## **Introduction**

To accommodate the diverse asset requirements of our fund, particularly operating on the Polygon blockchain, we introduce the "Synthetic Token" contract. This contract creates synthetic tokens as proxies for assets not readily available or lacking liquidity on traditional ERC-20 platforms or decentralized exchanges like Uniswap.

## **What are Synthetic Tokens?**

Synthetic tokens are digital assets that represent other real-world or digital assets within a blockchain environment. These tokens mirror the performance and value of their underlying assets. For our fund, synthetic tokens are backed in real-time by corresponding assets, enhancing liquidity and enabling participation in markets otherwise inaccessible on the Polygon network.

## **Features**

* **Real-Time Backing:** Each synthetic token is backed by a corresponding asset, with proof of reserve provided in real-time on the dashboard.
* **ERC-20 Standard:** Adopts the ERC-20 standard for compatibility, facilitating easy integration with wallets and exchanges.
* **Role-Based Access:** Utilizes the `AccessControl` module to manage permissions and secure token operations like minting and burning.

## **Key Components and Functions**

### **Variables**

| Variable      | Type   | Description                                                 |
| ------------- | ------ | ----------------------------------------------------------- |
| `_decimals`   | uint8  | Fixed to 18, standardizing the token's fractional unit.     |
| `_identifier` | string | Unique symbol of the underlying asset the token represents. |

### **Functions**

| Function Name | Parameters        | Description                                             |
| ------------- | ----------------- | ------------------------------------------------------- |
| `mint`        | `account, amount` | Mints tokens to a specified account, increasing supply. |
| `burn`        | `account, amount` | Burns tokens from a specified account, reducing supply. |
| `identifier`  | None              | Returns the asset symbol that the token represents.     |

## **Use Cases**

### **Enhanced Asset Accessibility:**

* Synthetic tokens facilitate investment in assets not directly accessible on the Polygon blockchain, broadening the fund's investment scope.

### **Liquidity Provision:**

* By representing less liquid assets, synthetic tokens provide the necessary liquidity to execute large trades without significant price impact.

### **Proof of Reserve:**

* Continuous proof of reserve ensures transparency and builds trust among investors by showing that each synthetic token is fully backed.

## **Security Measures**

* **Managed Access:** The minting and burning of tokens are tightly controlled through role-based permissions, ensuring that only authorized personnel can modify the supply.

***



## **Conclusion**

The "Synthetic Token" contract is crucial for bridging the gap between different blockchain ecosystems and enhancing the liquidity of assets within our fund. By leveraging synthetic tokens, the fund can effectively manage a diverse portfolio, maintaining alignment with its strategic investment goals while ensuring high standards of security and transparency.
