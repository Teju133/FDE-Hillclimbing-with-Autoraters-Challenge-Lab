---
name: analyze-flood-risk
description: Investigates subject and neighboring property FEMA flood-zone designations and hydrological risks.
metadata:
  adk_additional_tools:
    - get_lot_data
---

# Analyze Flood Risk Skill

When evaluating environmental or geographic flood risks for a property:

1. Retrieve and inspect the subject property's record using `get_lot_data`.
2. Identify the subject property's exact `plot_id`, `flood_zone`, `adjacent_parcels`, `topography`, and `soil_classification`, where available.
3. Do not restrict the investigation to the subject property.
4. For EVERY lot ID listed in the subject property's `adjacent_parcels` field, call `get_lot_data` using that neighboring lot ID.
5. Inspect each neighboring property's exact `flood_zone`, `topography`, and `soil_classification`, where available.
6. Explicitly report the neighboring lot IDs and their FEMA flood-zone classifications. Do not simply state that neighboring properties exist.
7. Compare the neighboring flood zones with the subject property's flood zone. Explain whether neighboring parcels have higher, lower, or comparable flood classifications.
8. Analyze potential shared flood exposure, drainage, and runoff implications using the available flood-zone, topography, and soil evidence.
9. Clearly distinguish verified database facts from potential hydrological implications. Do not claim a specific runoff direction, drainage connection, or water-flow pathway unless the data establishes it.
10. If drainage measurements, elevation data, or hydrological information are unavailable, explicitly identify those limitations and recommend appropriate survey or hydrological due diligence.
11. Never invent neighboring parcel IDs, flood-zone classifications, or environmental measurements.

## Required Report Output

Include a section titled **Neighboring Property Flood Risk Analysis**.

Where adjacent parcel records are available, include a table with:

| Neighboring lot | FEMA flood zone | Relevant observations |
|---|---|---|

After the table:

- Compare the subject property's flood zone with each adjacent property's flood zone.
- Explain potential implications for shared flood exposure, surface-water drainage, and development feasibility.
- Identify any available topography and soil evidence relevant to drainage.
- State any missing hydrological information that requires further investigation.

The analysis must be specific to the actual subject and neighboring lot records. A discussion of only the subject property's flood zone is insufficient.
