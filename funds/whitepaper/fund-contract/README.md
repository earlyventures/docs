---
description: >-
  Details the operations of our DeFi platform's main contract, managing
  investments, rebalancing, and fee structures, ensuring secure and efficient
  asset management.
---

# Fund

## **Introduction**

The "Fund" contract is a central component of our DeFi platform designed to manage a portfolio of digital assets. Utilizing the Solidity programming language and deployed on the Ethereum blockchain, this contract handles the core functionalities such as asset allocation, fees management, and interactions with tokens representing fund shares.

## How it works

### **Investor**&#x20;

* Investors can deposit currency into the fund in exchange for fund shares. This process involves the fund's strategy to allocate the deposited assets among various tokens according to predefined weights.

### Index Calculation

#### **Introduction to NAV Calculation**

The Net Asset Value (NAV) of a fund is a critical metric that represents the price per share of the fund. In our Earlyventures platform, the NAV calculation starts with a simple and intuitive benchmark: each share is initially valued at 1 USDT when the index begins. This approach allows for straightforward tracking of the fund's performance over time.

#### **Performance Tracking**

Using the initial NAV of 1 USDT as a baseline, the performance of the fund can be easily quantified by observing the current NAV. For example, if the NAV of the Crypto100 fund reaches 3.5 USDT, it indicates that the fund has achieved a 250% increase in value. This measurement provides a clear and easily understandable way to compare performance across different funds within the platform.

#### **Mechanism of NAV Calculation**

The NAV is calculated by summing the current market value of all assets held by the fund and then dividing by the total number of outstanding shares. This calculation is performed in real-time by the fund's smart contracts, ensuring that the NAV reflects the most current market conditions. The Asset Controller contract plays a crucial role in providing accurate and up-to-date asset valuations, which feed into the NAV computation.

**Importance of NAV in Investment Decisions**

The NAV is not just a number—it's a comprehensive reflection of the fund's overall health and performance. Investors use the NAV to make informed decisions, comparing it against historical values to assess growth, and evaluating potential investments based on how well the fund is performing relative to its peers.

By starting the NAV at 1 USDT, Earlyventures simplifies the investor's experience, making it easy to gauge fund performance at a glance. The dynamic calculation of the NAV, supported by sophisticated blockchain technology, ensures transparency and accuracy, providing investors with confidence in their investment choices on the platform.

### **Fee Collection**

* The contract periodically calculates and collects management and performance fees based on the fund's rules. These fees are taken from the fund's assets and converted to the primary currency token.

### **Rebalancing Portfolio**

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



***





## **Conclusion**

The "Fund" contract provides a robust and flexible foundation for managing a decentralized investment fund. With built-in upgradeability and security features, it offers a scalable solution for asset management on the blockchain.
