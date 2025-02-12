# BoulderRoller: Realistic Economic Analysis with Emission-Adjusted Price Models

## Abstract

We present a quantitative analysis of BoulderRoller's dual emission system, with specific focus on emission-based price pressure and realistic market capitalization projections. This paper provides a data-driven examination of token price formation, accounting for both TSS-based minting and vault yields, while considering realistic market absorption capacity.

## 1. Protocol Emission Mechanics

### 1.1 Dual Supply Structure

```typescript
interface EmissionSystem {
    daily_creation: {
        tss_minting: "user_count * avg_tss * 10",
        vault_yields: "segment_crosses * segment_tax(tvl_weighted)",
        total_rate: "Combined emissions from both sources"
    },

    emission_example: {
        // For 100 active users
        tss_emission: {
            users: 100,
            avg_tss: 45,
            daily_dung: 45,000
        },
        
        vault_emission: {
            avg_segments_crossed: 300,
            avg_tax: 200,
            daily_dung: 60,000
        }
    }
}
```

## 2. Price Formation Model

### 2.1 Supply Pressure Analysis

```yaml
daily_absorption_requirements:
  genesis_phase:
    daily_emission: 100,000 DUNG
    price_target: $0.01
    required_inflow: $1,000/day
    realistic_inflow: $500-1,500/day
    sustainable_price: $0.005-0.015

  month_1:
    daily_emission: 250,000 DUNG
    price_target: $0.015
    required_inflow: $3,750/day
    realistic_inflow: $2,000-4,000/day
    sustainable_price: $0.008-0.016
```

### 2.2 Market Absorption Capacity

```typescript
interface MarketCapacity {
    early_phase: {
        daily_new_users: 5-10,
        avg_investment: "$100-500",
        daily_inflow: "$500-5,000",
        sustainable_price: "Based on emission absorption"
    },

    growth_phase: {
        daily_new_users: 20-50,
        avg_investment: "$200-1,000",
        daily_inflow: "$4,000-50,000",
        price_ceiling: "Limited by emission pressure"
    }
}
```

## 3. Realistic Growth Projections

### 3.1 Month 3 Analysis

```typescript
interface Month3Metrics {
    network_state: {
        users: 500,
        daily_activities: 300,
        avg_tss: 45,
        segments: 200
    },

    emissions: {
        tss_based: 225,000 DUNG,
        vault_yields: 180,000 DUNG,
        total_daily: 405,000 DUNG,
        total_supply: "~15M DUNG"
    },

    price_mechanics: {
        required_daily_inflow: "$8,100 at $0.02",
        realistic_inflow: "$5,000-10,000",
        sustainable_price: "$0.02-0.03",
        market_cap: "$300,000-450,000"
    }
}
```

### 3.2 Month 6 Projections

```yaml
month_6:
  network_metrics:
    users: 2,500
    daily_activities: 1,500
    segments: 750
    
  emission_data:
    tss_based: 1.1M DUNG/day
    vault_yields: 1.5M DUNG/day
    total_daily: 2.6M DUNG
    total_supply: ~100M DUNG

  price_analysis:
    required_daily_inflow: "$130,000 at $0.05"
    realistic_inflow: "$50,000-100,000"
    sustainable_price: "$0.05-0.07"
    market_cap: "$5M-7M"
```

## 4. Economic Equilibrium Factors

### 4.1 Price Support Mechanisms

```typescript
interface PriceSupport {
    utility_value: {
        segment_creation: "1,000 DUNG cost",
        staking_requirements: "TVL competition",
        governance_rights: "Protocol control"
    },

    natural_sinks: {
        segment_creation: "Network expansion",
        staking_locks: "Yield generation",
        failed_attempts: "Competition mechanics"
    }
}
```

### 4.2 Supply Absorption

```yaml
absorption_mechanics:
  primary_drivers:
    - New user acquisition
    - Staking demand
    - Segment creation
    - Protocol growth

  realistic_limits:
    early_phase: "$5,000-10,000 daily inflow"
    growth_phase: "$50,000-100,000 daily inflow"
    mature_phase: "$100,000-250,000 daily inflow"
```

## 5. Valuation Framework

### 5.1 Emission-Adjusted Price Models

```typescript
interface PriceModel {
    base_calculation: {
        sustainable_price = daily_inflow / daily_emission,
        buffer_factor: 0.8, // Conservation factor
        max_price: daily_inflow * buffer_factor / daily_emission
    },

    price_ceiling: {
        month_3: "$0.03",
        month_6: "$0.07",
        month_12: "$0.15"
    }
}
```

### 5.2 Growth Scenarios

```yaml
scenarios:
  conservative:
    month_6:
      daily_emission: 2M DUNG
      daily_inflow: $40,000
      price: $0.02
      market_cap: $2M

  base_case:
    month_6:
      daily_emission: 2.6M DUNG
      daily_inflow: $130,000
      price: $0.05
      market_cap: $5M

  optimistic:
    month_6:
      daily_emission: 3M DUNG
      daily_inflow: $210,000
      price: $0.07
      market_cap: $7M
```

## 6. Risk Analysis

### 6.1 Emission Risks

```typescript
interface EmissionRisks {
    supply_pressure: {
        early_phase: "High relative to market cap",
        growth_phase: "Requires significant inflow",
        mature_phase: "Dependent on network growth"
    },

    mitigation_strategies: {
        emission_control: "Natural physical limits",
        price_support: "Utility value creation",
        market_growth: "User acquisition focus"
    }
}
```

### 6.2 Market Risks

```yaml
market_risks:
  supply_absorption:
    - Limited early market capacity
    - Emission/demand mismatch
    - Price discovery challenges
    
  stability_factors:
    - Utility-driven demand
    - Network effect growth
    - Natural emission limits
```

## 7. Conclusion

BoulderRoller's dual emission system creates significant price pressure that must be carefully considered in valuation models. Our analysis suggests sustainable price points significantly lower than initial projections, but with strong fundamentals for long-term growth based on utility value and network effects.

## Appendices

### A. Detailed Emission Models
[Supply growth calculations and absorption rates]

### B. Price Formation Analysis
[Market capacity and inflow requirements]

### C. Growth Scenarios
[Detailed network growth projections]

