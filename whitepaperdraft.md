# BoulderRoller: A Decentralized Gamified Fitness Ecosystem on Solana

## Table of Contents
- [Abstract](#abstract)
- [1. Introduction](#1-introduction)
- [2. Problem Statement](#2-problem-statement)
- [3. Token System](#3-token-system)
- [4. Protocol Mechanics](#4-protocol-mechanics)
- [5. Technical Architecture](#5-technical-architecture)
- [6. Growth Model](#6-growth-model)
- [7. Conclusion](#7-conclusion)

## Abstract

BoulderRoller reimagines fitness tracking by blending Strava-like competition with a zero-start token economy. The platform mints DUNG tokens solely through verified Total Segment Score (TSS) achievements, while using kCAL as a daily-refreshing utility token for segment access. This dual-token system creates a transparent and efficient reward mechanism that scales naturally with user participation.

## 1. Introduction

Modern fitness applications excel at tracking but fall short in sustainable rewards and engagement. BoulderRoller addresses this through a carefully designed token economy built on Solana, where every workout contributes to both personal achievement and economic participation. Our zero-start approach ensures all tokens are backed by real physical activity.

## 2. Problem Statement

Current fitness platforms face several challenges:

* **Fair Launch**: Traditional token systems often start with pre-mines or unfair distributions
* **Value Backing**: Tokens rarely represent real physical achievement
* **Sustainable Economics**: Most systems lack natural growth limitations
* **Engagement Incentives**: Limited rewards for consistent participation

## 3. Token System

### 3.1 Dual Token Structure

#### DUNG Token
* **Generation**: Minted solely through TSS achievements (10 DUNG per TSS)
* **Utility**: Staking, governance, and KoM challenges
* **Supply**: Zero initial supply, grows with network activity

#### kCAL Token
* **Distribution**: 2,000 daily allocation per user
* **Usage**: Required for segment access
* **Mechanics**: Burned through segment taxes
* **Reset**: Daily refresh at UTC 0:00

### 3.2 Economic Mechanics

* **Segment Tax**: distance * (segment_tvl/total_tvl)
* **Tax Collection**: Paid exclusively in kCAL
* **Burn Rate**: 80% of collected kCAL burned
* **Treasury**: 20% of collected kCAL to protocol

## 4. Protocol Mechanics

### 4.1 Activity Verification
* GPS validation for workout data
* TSS calculation and verification
* Segment completion tracking

### 4.2 Token Generation
* Initial activity: 1,000 DUNG (100 TSS example)
* Continuous minting: 10 DUNG per verified TSS
* Natural limitations through human capacity

### 4.3 Value Capture
* Segment taxes create natural kCAL demand
* TVL-weighted tax system
* Automated burn mechanism

## 5. Technical Architecture

### 5.1 Smart Contracts
* Token logic for DUNG and kCAL
* TSS verification system
* Segment tax calculation and collection
* Automated burn mechanism

### 5.2 Security Features
* GPS data validation
* Anti-gaming mechanisms
* Automated tax processing

## 6. Growth Model

### First Month
* Target Users: 50
* Daily Activities: 30
* Average TSS: 80
* Expected Supply: ~1.2M DUNG
* Staking Ratio: 60%

### Quarter One
* Target Users: 500
* Daily Activities: 300
* Average TSS: 85
* Expected Supply: ~12.75M DUNG
* Staking Ratio: 70%

### Six Months
* Target Users: 2,500
* Daily Activities: 1,500
* Expected Supply: ~63.75M DUNG
* Staking Ratio: 75%

## 7. Conclusion

BoulderRoller's zero-start, TSS-based token system creates a truly fair and sustainable fitness economy. By backing every token with verified physical activity and implementing natural supply growth limitations, we establish a platform where value directly correlates with network participation and achievement.

---

For technical details or inquiries, please contact Higher Logic Studios.
