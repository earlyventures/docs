---
description: >-
  Details how users invest in the Earlyventures fund,  highlighting investment,
  capital deployment via smart contracts, and automated share issuance for
  transparency and efficiency.
---

# Whitepaper

## How it works

### High-Level Fund Operation Overview

<figure><img src="../.gitbook/assets/process-ezgif.com-video-to-gif-converter.gif" alt=""><figcaption></figcaption></figure>

### **1. Investment Initiation**

Users invest USDT on the Polygon blockchain. Polygon is chosen not due to exclusive preference, but because it offers an optimal balance between gas costs, transaction capacity, and widespread acceptance by centralized exchanges (CEXs). Investments are made directly by transferring USDT from the user's wallet to the smart contract, ensuring that Earlyventures does not control the funds at any point in this process.

### **2. Capital Deployment**

Once the fund receives the USDT, it is deployed according to the fund's predefined strategy. This involves allocating the capital across various assets based on their respective weights within the portfolio. The actual deployment of capital is managed by a separate contract known as the "Asset Controller." This contract handles direct investments through DEX swaps for some tokens, while for others, it involves the creation of synthetic tokens that represent the assets on the Polygon blockchain.

### **3. Asset and Fund Management**

After deploying the capital, the Controller sends the acquired tokens back to the fund and updates the Net Asset Value (NAV) and Total Asset Value (TLV) in real-time based on the prices provided by the Controller. This real-time price updating ensures that the fund's valuation reflects current market conditions accurately.

### **4. Share Issuance**

The Fund Contract then issues shares in response to the investment. These shares are represented as tokens created by the "Fund Token Contract." Once minted, these share tokens (fund tokens) are sent directly to the investor's wallet, signifying their ownership and claim over a portion of the fund's assets.

This overview provides investors and stakeholders with a clear picture of the fund's operational mechanics, emphasizing transparency, efficiency, and security facilitated through the use of smart contracts on the blockchain. This setup not only simplifies the investment process but also enhances trust by automating asset management and share distribution.



***



Smart contract\



In our DeFi platform, the investment ecosystem is built around four core smart contracts that interoperate to provide a robust and secure framework for managing digital assets. These contracts include:

1. **Fund Contract**: Central to the platform, this contract handles the primary operations of asset management, including deposits, withdrawals, and fee collection. It operates with an array of tokens and integrates strategic allocation methods to balance the portfolio according to predefined criteria.
2. **Fund Token Contract**: This contract issues and manages tokens that represent shares in the fund. These tokens are held by investors as proof of their participation and claim on the fund's assets. The token mechanics ensure that shares are minted upon deposits and burned during withdrawals, directly linking the fund’s equity to the circulating token supply.
3. **Controller Contract**: Serving as the administrative backbone, this contract provides the necessary controls and permissions for the operation of the fund. It facilitates the implementation of management strategies, enforcement of fees, and other administrative tasks essential to the fund's operation.
4. **Synthetic Token Contract**: This contract manages the creation and operation of synthetic assets. These tokens are derivatives that represent other real or virtual assets and are used within the fund to achieve broader exposure and hedging capabilities without holding the underlying assets directly.

Together, these contracts form a comprehensive system designed to offer a transparent, efficient, and secure investment platform, leveraging blockchain technology to democratize access to asset management services.



<table data-view="cards"><thead><tr><th align="center"></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td align="center">Fund Contract</td><td><a href="whitepaper/fund-contract.md">fund-contract.md</a></td><td><a href="../.gitbook/assets/contract_fund (1).png">contract_fund (1).png</a></td></tr><tr><td align="center">Fund Token Contract</td><td><a href="whitepaper/fund-token.md">fund-token.md</a></td><td><a href="../.gitbook/assets/contract_fundtoken (1).png">contract_fundtoken (1).png</a></td></tr><tr><td align="center">Controler Contract</td><td><a href="whitepaper/controller-contract.md">controller-contract.md</a></td><td><a href="../.gitbook/assets/contract_controler (1).png">contract_controler (1).png</a></td></tr><tr><td align="center">Synthetic Token Contract</td><td><a href="whitepaper/synthetic-token-contract.md">synthetic-token-contract.md</a></td><td><a href="../.gitbook/assets/contract_synthetic (1).png">contract_synthetic (1).png</a></td></tr><tr><td align="center"></td><td></td><td></td></tr></tbody></table>









