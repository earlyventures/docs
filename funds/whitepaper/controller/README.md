---
description: >-
  The controller system is essential for managing capital deployment of the Fund
  and ensuring efficient asset operations.
---

# Controller

## **High-Level Functionality**

The controller system is tasked with managing two primary functions:

1. **Asset Management**: Depending on the token's characteristics and availability on the Polygon network, the appropriate controller is selected to manage its interactions, including swaps, liquidity provision, and price tracking.
2. **Asset Optimization**: Each controller optimizes the assets under its management, ensuring that the fund's operations are efficient and align with the current market conditions.

## **Controllers Description**

### **Synthetic Controller**:

* **Purpose**: Manages synthetic tokens which are representations of non-native assets on Polygon or assets without sufficient liquidity pools.
* **Functionality**: Facilitates the creation, pricing, and exchange of synthetic tokens, ensuring that they accurately mirror the value of the underlying assets they represent.

### **Uniswap Controller**:

* **Purpose**: Handles asset interactions for tokens that have existing liquidity pools on the Polygon network, such as WETH or WBTC.
* **Functionality**: Leverages the Uniswap v3 protocol to manage token swaps, liquidity provisioning, and real-time pricing, ensuring efficient market operations.

## **Operational Strategy**

The fund dynamically selects between controllers based on the specific requirements of each asset. This strategy allows the fund to maintain high liquidity, ensure accurate asset valuation, and optimize transaction costs and speeds.

* **Asset Availability and Liquidity Needs**: Assets with existing liquidity on Uniswap are managed by DEX controller like the Uniswap Controller, while those without are handled by the Synthetic Controller, which constructs a synthetic representation for trading and valuation purposes.
* **Market Responsiveness**: Controllers are equipped to adjust their operations in response to market changes, ensuring that the fund's portfolio remains robust and its operations remain scalable.

## **Conclusion**

Our controller system is a cornerstone of the fund's architecture, enabling flexible and efficient management of diverse assets on the Polygon network. By distinguishing between synthetic and existing assets, the system not only enhances fund performance but also broadens the scope of accessible investment opportunities, making it a vital component.
