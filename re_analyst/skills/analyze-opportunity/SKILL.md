---
name: analyze-opportunity
description: Investigates a land parcel for real estate investment opportunity analysis, including explicit acquisition cost-per-acre calculations.
metadata:
  adk_additional_tools:
    - get_lot_data
---

# Analyze Opportunity Skill

When asked to investigate a property or analyze an investment opportunity for a lot:

1. Use the `get_lot_data` tool to retrieve the subject property using its exact lot ID.
2. Review the acreage, zoning, last sale price, parcel APN, and other relevant property attributes.
3. Calculate acquisition cost per acre whenever both `last_sale_price` and `acreage` are available and valid numeric values.

   Required formula:

   Cost per acre = Last sale price / Acreage

4. Show the actual numerical calculation in the report. For example:
   `$310,000 / 3.1 acres = $100,000 per acre`.

5. Explicitly label the result as **Acquisition Cost per Acre** and highlight it as a key valuation metric. Do not merely list the sale price and acreage separately.
6. Do not invent or estimate missing prices or acreage. If either value is missing or invalid, clearly state that the calculation cannot be completed from the available records.
7. Consult the `analyze-flood-risk` skill to investigate the subject property's flood risk and adjacent properties.
8. Consult the `analyze-tax-implications` skill to investigate property tax holding costs and assessment records using the parcel APN.
9. Incorporate the findings into the investment analysis and explain their implications for acquisition and development feasibility.
