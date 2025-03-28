# Aviation Safety Analysis and Feasibility Study

This comprehensive report analyzes the airline feasibility study conducted by Collins Nyagaka. It examines aviation accident data to derive safety metrics and operational insights for the airline industry to support investment into plane purchases. The analysis provides valuable information for airline operators, safety regulators, and aviation stakeholders seeking to enhance safety protocols and operational efficiency.

## Data Overview and Processing Methodology

The analysis utilizes two primary datasets merged to create a comprehensive view of aviation safety across the United States. The first dataset, AviationData.csv, contains detailed accident records including event dates, location information, aircraft specifications, injury statistics, and environmental conditions. The second dataset, USState_Codes.csv, provides state abbreviations that allow for geographic classification of incidents.

The data preparation process involved several key steps to ensure data quality and usability. Initially, the 'Location' column was split into distinct 'Location' (city) and 'Abbreviation' (state) fields, with proper string cleaning applied to remove extraneous spaces. This preprocessing step was crucial for enabling the subsequent inner join between the datasets on the 'Abbreviation' field, creating a unified dataset that links accident data with specific U.S. states.


### Aircraft Manufacturer Standardization

The preprocessing includes standardization of aircraft manufacturer information (Make_Standardized), with the sample showing manufacturers including Piper, Cessna, and Beech. This standardization enables more reliable comparative analysis between different aircraft types and manufacturers, potentially revealing important patterns in safety performance across the industry.

### Data Structure and Key Variables

The merged dataset contains 33 columns, capturing multiple dimensions of aviation safety:

- Temporal data: Event dates spanning decades of aviation history
- Geographic information: Detailed location data including coordinates
- Aircraft specifications: Make, model, and configuration details
- Safety outcomes: Fatality and injury statistics
- Environmental factors: Weather conditions at time of incident
- Operational context: Flight phase when incidents occurred

The final dataset has been further enhanced with derived metrics including standardized manufacturer information, extracted year data, and most significantly, calculated safety indices and severity scores that quantify different aspects of aviation risk.

## Safety Metrics Development

The analysis introduces several sophisticated safety metrics that transform raw accident data into actionable intelligence:

### Safety Index

A composite metric visible in the final dataset (value range approximately 1.3-2.0 in the visible samples) quantifies overall safety performance. This index likely incorporates multiple factors including accident severity, aircraft type, and potentially temporal trends. The methodology for calculating this index represents a valuable contribution to aviation safety assessment, providing a standardized way to compare safety across different aircraft types, regions, or time periods. Models like the Cessna 152 and Piper PA-28 consistently rank high, suggesting a lower overall risk profile. These models are often favoured for training and recreational flying due to their established safety records. Deeper analysis could involve comparing safety indexes within specific aircraft categories (e.g., single-engine, multi-engine) for a more targeted recommendation.[Aircraft Safety Index Analysis](https://public.tableau.com/shared/FMFN83XY3?:display_count=n&:origin=viz_share_link)

### Severity Score

The dataset includes a Severity Score that measures the impact of incidents, with a value of 2.0 visible across multiple sample records.  This metric considers factors such as fatalities, injuries, and aircraft damage to create a standardized measure of incident severity.

California not only has the most accidents but also the highest number of fatal accidents and destroyed aircraft. ![Injury Severity in top states](https://github.com/user-attachments/assets/8d79347d-c6bd-42f0-b8b0-b19a6e28eb09)
![Aircraft Damage distribution in top states](https://github.com/user-attachments/assets/3726bf53-007c-4138-9171-d2667885fe2f)


Alaska, despite being fourth in total accidents, has a higher proportion of IMC-related accidents, suggesting challenging weather conditions play a significant role in accidents there. [Weather Conditions Distribution](images/States airline accidents.png)

All states show a similar pattern of substantial aircraft damage being the most common outcome, followed by destroyed aircraft.

### Weather Resilience

A Weather_Resilience metric ranges from 0.0 to 1.0 in the visible data, which is a scale that quantifies how well aircraft perform under various weather conditions. This innovative metric could be particularly valuable for airlines operating in regions with challenging weather patterns, providing guidance on which aircraft types demonstrate better performance in adverse conditions.

The chart shows that VMC (Visual Meteorological Conditions) is the most common weather condition during accidents across all top states. California, Texas, and Florida show similar weather pattern distributions, while Alaska has a higher proportion of IMC (Instrument Meteorological Conditions) accidents compared to other states. Alaska, despite being fourth in total accidents, has a higher proportion of IMC-related accidents, suggesting challenging weather conditions play a significant role in accidents there.![States airline accidents](https://github.com/user-attachments/assets/cccab7dd-672c-41a7-a880-b5ebcc7914d7)


The predominance of VMC(Visual Meteorological Conditions) conditions across all states indicates that most accidents occur in good visibility conditions, suggesting that factors other than weather (such as pilot error or mechanical issues) may be primary contributors.!![Accidents by weather conditions](https://github.com/user-attachments/assets/d6da5d3c-3409-4bba-a943-15958f2a1b3c)



## Temporal Analysis and Safety Trends

The dataset spans multiple decades of aviation history, with records from 1948 through 2022. This extensive temporal coverage enables analysis of safety evolution across different eras of aviation technology and regulation. The implementation of a year extraction from event dates facilitates trend analysis and enables the identification of patterns in safety improvements over time.


Notably event occurrences have reduced steadily over time. ![Accidents trend over time](https://github.com/user-attachments/assets/05c8441a-fd7c-4a1d-9432-79477215cd17)


### Avoid High-Risk Regions: Use the geographic analysis to avoid operating in high-risk areas.

Geographic Analysis: The analysis highlights California, Texas, Florida, and Alaska as having a high frequency of accidents. This could be due to factors like higher air traffic density, challenging terrain, or specific weather patterns in these regions. Further investigation involved mapping accident locations within these states to identify potential hotspots or areas requiring extra caution. Consider using external resources like aviation safety databases or FAA reports to supplement this analysis.![Geographical distribution of events occurrences in different states](https://github.com/user-attachments/assets/39aa3d9c-1860-4f0a-8116-d4f2ea6f416e)


## Actionable Insights for Industry Stakeholders

Based on the analysis structure and metrics developed, several actionable insights can be derived for different aviation stakeholders:

### For Airline Operators

1. **Fleet Composition Strategy**: The analysis of Safety_Index by aircraft manufacturer provides guidance for fleet acquisition and retirement decisions. Operators should prioritize aircraft with consistently higher safety ratings when planning fleet expansions or replacements.

2. **Weather Operation Protocols**: The Weather_Resilience metric offers a data-driven foundation for developing standard operating procedures specific to different weather conditions. Aircraft with lower resilience scores may require more conservative operational guidelines in challenging weather situations.

3. **Training Emphasis Based on Flight Phase Risk**: The inclusion of "Broad.phase.of.flight" data allows for identification of higher-risk phases (such as approach, takeoff, or cruise) that should receive additional focus during pilot training and operational reviews.

### For Regulatory Authorities

1. **Evidence-Based Regulation Development**: The comprehensive safety metrics provide quantitative support for regulatory decisions, enabling more targeted and effective safety requirements based on demonstrated risk factors.

2. **Regional Safety Focus**: The state-by-state geographic breakdown allows regulatory authorities to identify regions that may require additional oversight or safety campaigns based on accident concentration.

3. **Aircraft Certification Insights**: Patterns in safety performance across different aircraft makes and models can inform certification requirements and inspection protocols for new and existing aircraft types.

## Implementation Recommendations

To maximize the value of this analysis for aviation stakeholders, several implementation strategies are recommended:

1. **Interactive Dashboard Development**: Create a live dashboard that allows stakeholders to filter and explore safety metrics by region, aircraft type, time period, and weather conditions to support data-driven decision-making. [Explore the interactive dashboard here](https://public.tableau.com/shared/C46W9R9FN?:display_count=n&:origin=viz_share_link)


2. **Predictive Model Integration**: Develop predictive models using the established safety metrics to forecast potential safety concerns before they manifest as incidents or accidents.

3. **Standard Operating Procedure Review Process**: Establish a systematic process for regular review and updating of standard operating procedures based on ongoing analysis of safety metrics and their correlations with operational factors.

4. **Cross-Industry Benchmarking Program**: Implement a voluntary benchmarking program that allows airlines to compare their safety performance against industry averages while maintaining appropriate confidentiality protections.

## Conclusion

The aviation safety analysis demonstrated in this project provides a robust framework for quantifying, comparing, and improving safety across the airline industry. By transforming raw accident data into standardized safety metrics, the analysis enables evidence-based decision-making for airlines, manufacturers, and regulatory authorities alike.

The Safety Index, Severity Score, and Weather Resilience metrics represent particularly valuable contributions that can drive concrete operational improvements. These insights can contribute to the industry's ongoing mission to enhance aviation safety when implemented as part of a comprehensive safety management system.

For future development, expanding the analysis to include economic factors, maintenance records, and operational efficiency metrics would further enhance its utility for feasibility studies and strategic planning in the airline industry. Additionally, extending the geographical scope beyond the United States would provide valuable global benchmarking capabilities for international operators.

## License

This project is licensed under the [MIT License](LICENSE). See the LICENSE file for more details.

