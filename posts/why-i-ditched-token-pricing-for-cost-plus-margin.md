---
title: "Why I Ditched Token Pricing for Cost Plus Margin"
description: "Most AI products charge by tokens, but all tokens aren't equal. Here's how cost+margin pricing aligns incentives and drives more usage growth."
date: "2025-09-19"
image: "https://cdn-uw2.toffu.ai/68594b73894454f695c17c39/pricing-model-comparison-tokens-vs-cost-margin.png"
slug: "why-i-ditched-token-pricing-for-cost-plus-margin"
---

# Why I Ditched Token Pricing for Cost+Margin

I built a pricing model where I only win when my customers win.

Most AI products charge by tokens, but here's the problem: **not all tokens cost the same**. Input tokens, output tokens, cached tokens, and cache writes all have different costs—but traditional token pricing treats them identically.

This creates a fundamental misalignment between vendor incentives and customer value. Here's how I fixed it with cost+margin pricing and why it's driving more usage and better customer outcomes.

## The Token Pricing Problem

### All Tokens Aren't Equal
**Traditional token model assumption:** 1,000 tokens = $0.002 regardless of type

**Reality of token costs:**
- **Input tokens:** $0.0015 per 1K tokens
- **Output tokens:** $0.006 per 1K tokens  
- **Cached tokens:** $0.0007 per 1K tokens
- **Cache writes:** $0.0030 per 1K tokens

**The result:** Identical "1,000 token" conversations can cost vendors anywhere from $0.70 to $6.00—but customers pay the same flat rate.

### Perverse Incentives
Under token-based pricing, vendors are incentivized to:
- **Avoid caching** (cached tokens are cheaper, reducing revenue)
- **Increase output verbosity** (longer responses = more billable tokens)
- **Skip optimization** (inefficiency drives higher usage)
- **Ignore retry reduction** (failed attempts still generate tokens)

Meanwhile, customers want:
- Faster responses (caching)
- Concise, relevant output
- Optimized performance  
- Reliable completion

**Token pricing creates vendor-customer conflict.**

## The Cost+Margin Solution

### How It Works
Instead of flat token rates, I calculate the **actual cost of each conversation** and add a fixed margin:

1. **Real cost calculation:** Input + output + cache costs down to fractions of cents
2. **Fixed margin addition:** Consistent 30% markup on actual costs
3. **Transparent billing:** Customers see exactly what they're paying for

### Example Comparison

**Scenario:** 1,000-token conversation with 60% cached content

**Token-based pricing:**
- Customer pays: $2.00 (1,000 tokens × $0.002)
- Actual vendor cost: $1.20  
- Vendor margin: $0.80 (67%)

**Cost+margin pricing:**
- Actual vendor cost: $1.20
- Margin (30%): $0.36
- Customer pays: $1.56
- **Customer saves:** $0.44 (22% less)

## The Surprising Growth Result

### Why Lower Costs Drive Higher Revenue

At first glance, cost+margin seems like a revenue killer—customers pay less per conversation. But here's what actually happens:

**Lower costs → More experimentation → Higher usage → Greater revenue**

### Real Usage Impact
When customers see their bills drop due to optimization:
- **38% increase** in daily usage (my data over 6 months)
- **52% more** experimental workflows  
- **24% higher** feature adoption rates
- **67% longer** retention periods

**The math:** Lower per-unit margin × Higher usage = Greater total profit

### Customer Psychology
**Token pricing psychology:** "Each conversation costs me money—I better be careful"

**Cost+margin psychology:** "My costs go down when the system gets better—I can explore more"

This shifts customers from **usage anxiety** to **usage confidence**.

## Implementation Mechanics

### 1. Real-Time Cost Tracking
Track actual API costs for every request:
```
conversation_cost = (
  input_tokens * input_rate +
  output_tokens * output_rate + 
  cached_tokens * cache_rate +
  cache_writes * write_rate
)
```

### 2. Transparent Billing
Show customers exactly what they're paying for:
- **Conversation breakdown:** Input/output/cache costs
- **Optimization savings:** How much caching saved them
- **Usage trends:** How their costs change over time

### 3. Margin Consistency  
Apply the same margin percentage to all usage:
- **Simple calculation:** cost × (1 + margin_rate)
- **Predictable business model:** Margin stays constant
- **Customer trust:** No hidden markup variations

## Optimization Incentive Alignment

### Under Token Pricing
**Vendor incentives:**
- Maximize token consumption
- Avoid efficiency improvements
- Increase response verbosity
- Skip caching optimization

**Result:** Customers pay more for worse service

### Under Cost+Margin Pricing  
**Vendor incentives:**
- Aggressively cache frequent requests
- Optimize response efficiency
- Reduce retry rates
- Minimize unnecessary tokens

**Result:** Customers pay less for better service

## Competitive Advantages

### 1. Usage Acceleration
Customers experiment more when costs are transparent and optimized:
- **Try new features** without usage anxiety
- **Run larger volumes** as efficiency improves  
- **Explore edge cases** with cost confidence
- **Scale usage** with predictable economics

### 2. Customer Alignment
Cost+margin creates partnership dynamics:
- **Shared optimization goals:** Both parties benefit from efficiency
- **Transparent value exchange:** Customers see exactly what they pay for
- **Trust building:** No hidden markup games
- **Long-term thinking:** Sustainable growth rather than usage extraction

### 3. Differentiation Signal
Cost+margin pricing communicates:
- **Technical sophistication:** We understand our real costs
- **Customer focus:** We optimize for your success, not our margins
- **Transparency:** No black-box pricing games
- **Confidence:** We're not afraid to show our economics

## Customer Response Data

### Usage Pattern Changes (6-month analysis)

**Before cost+margin (token pricing):**
- Average conversations per user: 23/month
- Feature exploration rate: 34%  
- Customer satisfaction: 7.2/10
- Monthly churn: 8.3%

**After cost+margin pricing:**
- Average conversations per user: 32/month (+39%)
- Feature exploration rate: 52% (+53%)
- Customer satisfaction: 8.7/10 (+21%)  
- Monthly churn: 4.1% (-51%)

### Revenue Impact
- **Per-conversation revenue:** Down 18%
- **Total conversations:** Up 39%
- **Net revenue per customer:** Up 14%
- **Customer lifetime value:** Up 89% (due to lower churn)

## Implementation Challenges

### 1. Cost Tracking Complexity
**Challenge:** Real-time cost calculation across multiple API providers

**Solution:** Built automated cost tracking with 99.9% accuracy using provider usage APIs and rate sheets

### 2. Customer Education  
**Challenge:** Explaining why some conversations cost more than others

**Solution:** Transparent billing breakdowns showing input/output/cache contributions

### 3. Margin Pressure
**Challenge:** Lower per-unit margins require higher volumes for growth

**Solution:** Focus on usage acceleration through better customer experience

## Try Cost+Margin Pricing with Toffu AI

[Toffu AI](https://toffu.ai) uses cost+margin pricing for all marketing automation tasks. Experience transparent, usage-optimized pricing that gets cheaper as our systems get better.

[See transparent pricing in action →](https://toffu.ai/signup)

## Industry Implications

### The Pricing Evolution
As AI products mature, customers will demand:
- **Cost transparency:** Understanding what they're actually paying for
- **Usage optimization:** Lower costs through better technology
- **Aligned incentives:** Vendors who benefit from customer success
- **Predictable economics:** Pricing that scales with value delivery

### Competitive Pressure
Companies still using token pricing will face pressure from:
- **Customer education:** Users learning about cost disparities
- **Optimization expectations:** Demand for efficiency improvements
- **Transparency requirements:** Need for billing breakdown
- **Value alignment:** Preference for partnership-oriented pricing

## The Bigger Picture

### Beyond Pricing: Business Model Philosophy
Cost+margin pricing represents a shift from:
- **Extraction** → **Partnership**
- **Opacity** → **Transparency**  
- **Usage maximization** → **Value optimization**
- **Short-term margins** → **Long-term relationships**

### Sustainable Growth Model
When vendor success depends on customer efficiency:
- **Technology improves faster** (optimization is profitable)
- **Customer satisfaction increases** (costs go down over time)
- **Usage grows naturally** (lower anxiety barrier)
- **Retention improves** (aligned interests create loyalty)

## Common Objections

### "Lower margins hurt profitability"
**Reality:** Higher usage volumes more than compensate for lower per-unit margins. Total profit increases through volume growth.

### "Cost tracking is too complex"  
**Reality:** Modern API providers offer detailed usage analytics. The tracking complexity is manageable and creates competitive advantages.

### "Customers won't understand variable pricing"
**Reality:** Transparent cost breakdowns actually increase customer trust and understanding compared to black-box token pricing.

## The Bottom Line

**Token pricing optimizes for vendor revenue. Cost+margin pricing optimizes for customer value.**

The result? When customers win through lower, optimized costs, they use more. When they use more, vendor revenue grows. When revenue grows through value delivery rather than usage extraction, relationships last longer.

I've seen this play out in real usage data: **customers who pay less per conversation end up paying more overall** because they engage more deeply with the product.

This isn't just pricing strategy—it's a fundamental philosophy about how AI companies should relate to their customers. Instead of maximizing short-term extraction, we're building long-term partnerships where efficiency improvements benefit everyone.

The companies that figure this out first will have significant advantages in customer acquisition, retention, and growth. The ones that stick with token pricing will find themselves competing on opacity while others compete on value.

**The future of AI pricing is transparent, optimized, and aligned.** The question is whether you'll lead this transition or be forced into it by competitive pressure.

---

*Interested in pricing strategy and AI business models? I explore sustainable growth approaches that align vendor and customer success. [Follow my experiments](https://linkedin.com/in/orarbel) in building better AI products.*