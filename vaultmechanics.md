# BoulderRollers Vault Mechanics

## Table of Contents
- [Overview](#overview)
- [Vault Intake & Auto-Minting](#vault-intake--auto-minting)
- [Yield Distribution Mechanics](#yield-distribution-mechanics)
- [Atomic Distribution](#atomic-distribution)
- [Technical Implementation](#technical-implementation)
- [Benefits](#benefits)
- [Conclusion](#conclusion)

## Overview

BoulderRollers leverages a fully automated vault mechanism to streamline yield distribution. The vault is designed to:

* **Receive kCAL Tokens**: When users incur kCAL taxes (for example, when crossing designated segments during rides), these tokens are automatically funneled into the vault.

* **Auto-Mint DUNG Tokens**: Upon receiving kCAL, the vault converts these tokens to DUNG tokens at a predetermined conversion rate (1:1). This conversion is performed automatically and without manual intervention.

* **Distribute Yield**: Newly minted DUNG tokens are immediately distributed to:
  * Vault Depositors (70%): Users who have staked their tokens and provided liquidity
  * KOM Holder (20%): The top performer on a designated segment, as determined by our Strava-modeled KOM system
  * Protocol Treasury (10%): Reserved for ongoing development, maintenance, and ecosystem growth

All of these steps occur in a single atomic transaction, ensuring efficiency, security, and transparency.

## Vault Intake & Auto-Minting

### How It Works

1. **Deposit of kCAL Tokens**
   * kCAL tokens generated as taxes from segment crossings are automatically sent to the vault
   * The vault is configured to listen for incoming kCAL token transfers

2. **Automatic Conversion**
   * Upon receipt, the vault triggers a conversion function
   * kCAL tokens are converted to DUNG tokens at a fixed 1:1 ratio
   * This conversion is implemented via smart contract logic that adheres to industry standards (similar to EIP-4626 for yield-bearing vaults)

3. **Minting Process**
   * The conversion function mints the corresponding amount of DUNG tokens
   * The minted tokens are then made available for distribution

## Yield Distribution Mechanics

Once DUNG tokens are minted, they are allocated as follows:

### Vault Depositors (70%)
* A majority share is rewarded to users who have deposited DUNG tokens into the vault
* Incentivizes long-term staking and liquidity provision

### KOM Holder (20%)
* The user holding the King of the Mountain (KOM) position on a high-yield segment receives a premium share of the yield
* This competitive element drives additional demand for staking and participation in the ecosystem

### Protocol Treasury (10%)
* A portion of the yield is reserved for the protocol treasury
* These funds support ongoing development, security audits, and ecosystem improvements

## Atomic Distribution

The entire process—from receiving kCAL tokens, auto-minting DUNG tokens, to distributing yields—is executed in a single atomic transaction. This means:

* **No Intermediate States**: The entire operation is completed as one indivisible step, ensuring that all changes are committed together
* **Increased Security and Efficiency**: Atomic transactions prevent potential exploits or errors that could occur if these steps were performed separately

## Technical Implementation

### Smart Contract Architecture

Our vault smart contract is designed with the following key components:

#### Deposit Function
Accepts kCAL tokens and triggers the conversion process.

```solidity
function depositKCAL(uint256 amount, address sender) external {
    // Transfer kCAL tokens from the sender to the vault
    kCALToken.transferFrom(sender, address(this), amount);
    // Trigger auto-minting and distribution
    _processYield(amount);
}
```

#### _processYield Function
Handles the conversion of kCAL to DUNG and distribution to recipients.

```solidity
function _processYield(uint256 kCALAmount) internal {
    // Convert kCAL to DUNG tokens at a 1:1 ratio
    uint256 dungAmount = kCALAmount; // 1:1 conversion rate
    _mint(address(this), dungAmount);
    
    // Calculate distribution amounts
    uint256 depositorShare = dungAmount * 70 / 100;
    uint256 komShare = dungAmount * 20 / 100;
    uint256 treasuryShare = dungAmount * 10 / 100;
    
    // Distribute tokens
    _distribute(depositorShare, komShare, treasuryShare);
}
```

#### _distribute Function
Executes the distribution of minted DUNG tokens.

```solidity
function _distribute(uint256 depositorShare, uint256 komShare, uint256 treasuryShare) internal {
    // Distribute to vault depositors
    vaultDepositorPool.distribute(depositorShare);
    // Reward the current KOM holder
    address currentKOMHolder = komManager.getCurrentKOM();
    _transfer(address(this), currentKOMHolder, komShare);
    // Allocate protocol fee to treasury
    _transfer(address(this), protocolTreasury, treasuryShare);
}
```

### Integration with EIP-4626

* **Standard Interface**: Our vault follows EIP-4626 guidelines for yield-bearing vaults, ensuring compatibility with other DeFi protocols
* **Transparency and Auditability**: All operations, including minting and distribution, are recorded on-chain and can be audited by third parties

## Benefits

* **Streamlined Operations**: Combining kCAL receipt, DUNG minting, and yield distribution into one atomic process minimizes gas costs and operational complexity

* **Enhanced User Experience**: Users benefit from immediate reward distribution without delays or manual interventions

* **Robust Security**: Atomic transactions reduce the risk of inconsistencies and exploits, ensuring that all participants receive the correct yield allocations

* **Interoperability**: By aligning with industry standards, our vault can easily integrate with other platforms and yield aggregators in the DeFi ecosystem

## Conclusion

The BoulderRollers vault mechanism is engineered for efficiency, security, and transparency. By automating the conversion of kCAL tokens into DUNG tokens and distributing them among vault depositors, the KOM holder, and the protocol treasury—all in a single atomic transaction—we create a seamless and robust yield distribution process.

This innovative design not only enhances the value proposition for our users but also sets a new standard for integrating real-world performance data with blockchain-based incentives.

---

For further technical details or developer inquiries, please refer to our full API documentation or contact our technical support team.

**BoulderRollers Documentation Team**  
For questions or feedback, please visit our developer forum or contact support@boulderrollers.io
