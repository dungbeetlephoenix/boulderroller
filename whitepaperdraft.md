# BoulderRoller: A Zero-Start Physical Activity Token System with Dual-Token Architecture

## Table of Contents

- [Abstract](#abstract)
- [1. Introduction](#1-introduction)
- [2. System Architecture](#2-system-architecture)
  - [2.1 Token Design](#21-token-design)
  - [2.2 Economic Foundations](#22-economic-foundations)
- [3. Protocol Mechanics](#3-protocol-mechanics)
  - [3.1 Token Generation](#31-token-generation)
  - [3.2 Segment Economics](#32-segment-economics)
- [4. Technical Implementation](#4-technical-implementation)
  - [4.1 Smart Contract Architecture](#41-smart-contract-architecture)
  - [4.2 Security Considerations](#42-security-considerations)
- [5. Economic Equilibrium](#5-economic-equilibrium)
  - [5.1 Supply Dynamics](#51-supply-dynamics)
  - [5.2 Value Capture](#52-value-capture)
- [6. System Benefits](#6-system-benefits)
- [7. Conclusion](#7-conclusion)
- [References](#references)
- [Appendix](#appendix)

## Abstract

We present BoulderRoller, a novel blockchain-based fitness protocol implementing a zero-start token system backed entirely by verified physical activity. The protocol introduces a dual-token architecture: a primary token (DUNG) minted exclusively through Total Segment Score (TSS) achievements, and a utility token (kCAL) implementing a daily-reset mechanism with deterministic burn rates. Through careful economic design, the system achieves natural supply growth limitations while maintaining incentive alignment between physical achievement and economic participation.

## 1. Introduction

Traditional fitness platforms have struggled to create sustainable token economies that genuinely reflect user achievement. Previous attempts at tokenizing fitness activity have often relied on pre-mines, arbitrary emission schedules, or complex multi-token systems that fail to maintain long-term economic viability. We present a system that directly ties token creation to verified physical work, implementing a zero-start mechanism that ensures every token in circulation represents actual athletic achievement.

## 2. System Architecture

### 2.1 Token Design

The protocol implements two distinct tokens with complementary functions:

#### 2.1.1 Primary Token (DUNG)

* Initial Supply: 0
* Minting Mechanism: TSS-based (10 DUNG per verified TSS)
* Use Cases:
  * Protocol governance
  * Stake-based competition
  * Performance bonds for KoM challenges

#### 2.1.2 Utility Token (kCAL)

* Daily User Allocation: 2,000 kCAL
* Reset Schedule: UTC 0:00
* Primary Function: Segment access fee denomination
* Burn Mechanism: 80% of collected fees

### 2.2 Economic Foundations

The system implements several key economic mechanisms:

```typescript
interface SystemMechanics {
    initial_state: {
        dung_supply: 0,
        first_activity: {
            tss: 100,
            initial_mint: 1000 DUNG,
            segments_crossed: 3
        }
    }

    kcal_mechanics: {
        daily_user_allocation: 2000,
        tax_calculation: {
            per_segment: "distance * (segment_tvl/total_tvl)",
            payment: "kCAL only",
            burn_rate: "80% of collected kCAL"
        }
    }
}
```

## 3. Protocol Mechanics

### 3.1 Token Generation

#### 3.1.1 TSS-Based Minting

The protocol mints DUNG tokens exclusively through verified TSS achievements:

* Minting Rate: 10 DUNG per TSS
* Verification Requirements:
  * GPS data validation
  * Segment completion verification
  * Anti-gaming checks

#### 3.1.2 Natural Supply Limitations

Supply growth is constrained by:

* Human TSS capacity (~300/day maximum)
* Physical recovery requirements
* Seasonal activity patterns

### 3.2 Segment Economics

#### 3.2.1 Access Fee Calculation

```typescript
interface SegmentTax {
    calculation: {
        base_rate: "distance_based",
        multiplier: "segment_tvl/total_tvl",
        payment_token: "kCAL only"
    }
}
```

#### 3.2.2 Fee Distribution

* Burn Rate: 80% immediate destruction
* Treasury Allocation: 20% of collected fees
* Dynamic Adjustment: Increases with network congestion

## 4. Technical Implementation

### 4.1 Smart Contract Architecture

#### 4.1.1 Token Contracts

* DUNG Token: Standard SPL token with minting controlled by TSS verification
* kCAL Token: Daily-reset utility token with burn mechanics

#### 4.1.2 Core Protocol Contracts

* TSS Verification System
* Segment Tax Calculator
* Automated Burn Mechanism
* TVL Tracking System

### 4.2 Security Considerations

#### 4.2.1 Activity Verification

* Multi-point GPS validation
* Speed and distance calculations
* Historical pattern analysis
* Segment completion verification

#### 4.2.2 Economic Security

* TVL-weighted tax calculations
* Automated burn mechanisms
* Dynamic fee adjustments

## 5. Economic Equilibrium

### 5.1 Supply Dynamics

The system achieves equilibrium through several mechanisms:

#### 5.1.1 Supply Growth

* Pure function of network TSS
* Natural physical limitations
* Seasonal variation handling

#### 5.1.2 Demand Drivers

* Segment competition
* Governance participation
* Staking requirements

### 5.2 Value Capture

```typescript
interface ValueCapture {
    segment_taxes: {
        collection: "kCAL only",
        distribution: {
            burn: "80%",
            treasury: "20%"
        }
    }
}
```

## 6. System Benefits

### 6.1 Economic Design

* Zero initial supply ensures fair distribution
* Physical backing for all tokens
* Natural supply growth limitations
* Sustainable economic mechanics

### 6.2 Incentive Alignment

* Direct correlation between effort and rewards
* Competition-driven demand
* Natural price discovery
* Sustainable token velocity

## 7. Conclusion

BoulderRoller presents a novel approach to fitness tokenization through its zero-start, dual-token architecture. By implementing strict TSS-based minting and automated burn mechanics, the system creates a sustainable economy where token value directly correlates with network activity and achievement. The careful balance between DUNG minting and kCAL utility provides both long-term value accrual and day-to-day functionality.

## References

[Relevant academic papers and technical specifications]

## Appendix

### A. Protocol Parameters

* Detailed TSS calculations
* Segment tax formulas
* Burn rate specifications

### B. Security Mechanisms

* GPS validation algorithms
* Anti-gaming systems
* Economic security measures

---

**Authors**: Higher Logic Studios Team  
**Contact**: Technical inquiries: support@boulderrollers.io
