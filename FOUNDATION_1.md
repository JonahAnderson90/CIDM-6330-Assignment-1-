
# FOUNDATION 1: Sprint Assignment

## 1. Dataset Selection Justification

**Source and Scope:**  
**Dataset:** BTS Airline On-Time Performance Data  
**Agency:** Bureau of Transportation Statistics (BTS)  
**Scope:** Records of airline on-time arrival and departure data for flights operated by large air carriers in the United States. Includes scheduled/actual times, delays, carrier codes, flight numbers, and airport codes.


**Access Verification:**
- Data is publicly available via the [BTS website](https://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp?pn=1) and can be downloaded as CSV files or accessed via the BTS API.
- Example data snippet (CSV):
- A verified extract of the dataset is included in the repository ([evidence/sample_BTS_Airline_On-Time_Performance.csv](evidence/sample_BTS_Airline_On-Time_Performance.csv)), containing representative rows from the BTS Airline On-Time Performance dataset and demonstrating successful data retrieval.

| Year | Month | DayofMonth | Carrier | FlightNum | Origin | Dest | DepTime | ArrTime | DepDelay | ArrDelay |
|------|-------|------------|---------|-----------|--------|------|---------|---------|----------|----------|
| 2023 | 1     | 15         | AA      | 100       | DFW    | LAX  | 0800    | 0930    | 5        | 10       |

- Downloaded sample file: (attach screenshot or file in your submission if required)

**Relational Depth:**
- Main flight records reference:
  - Carrier codes (from carrier lookup table)
  - Airport codes (from airport lookup table)
- These relationships allow joining flight data with carrier and airport metadata for richer analysis.

**Temporal Characteristics:**
- Update frequency: Monthly
- Historical depth: Data available from 1987 to present
- Time granularity: Daily (with actual timestamps for each flight)

**Why this dataset:**
- Rich, real-world scenario for architectural thinking, with large volumes of data, multiple relationships, and business relevance. Airline performance and delay analysis are widely applicable and interesting for both technical and practical reasons.

---

## 2. Initial Problem Space

**Domain Observations:**
- Data includes detailed records for each flight, with delay reasons, scheduled and actual times, and references to carriers and airports.
- Patterns: Seasonal and weather-related delays, hub airports with more traffic, certain carriers with more/less delays.
- Gaps: Some flights may have missing or incomplete data; not all delay causes are always specified.

**Candidate Problems:**
1. Predict flight delays for a given route and time of day.
2. Analyze which airports or carriers have the highest average delays.
3. Identify trends in delay causes over time (e.g., weather vs. carrier-related).
4. Optimize flight scheduling to minimize delays.
5. Assess the impact of specific events (e.g., holidays, weather events) on flight punctuality.

**Questions You Can't Yet Answer:**
- How complete and clean is the data for all years and carriers?
- Are there any access or licensing restrictions for large-scale data use?
- What is the best way to join and normalize the related tables?
- How much data is missing for delay causes or other key fields?

---

## 3. Architecture Characteristics Discovery

**Candidate Characteristics:**
1. Scalability: The system must handle large volumes of historical and incoming data.
2. Availability: High availability is important for real-time or near-real-time analytics.
3. Performance: Fast query and analysis response times are needed for user-facing dashboards.
4. Data Integrity: Ensuring accuracy and consistency across joined tables is critical.
5. Security: Protecting sensitive or proprietary data (if any) is necessary.
6. Modifiability: The architecture should allow for easy addition of new data sources or analytics features.
7. Interoperability: Ability to integrate with external systems (e.g., weather APIs, airline systems).

**Tensions You Anticipate:**
- Scalability vs. Performance: Optimizing for one may impact the other.
- Data Integrity vs. Modifiability: Strict integrity checks can make changes harder.
- Availability vs. Security: More open systems may be less secure.

**What You Don't Know Yet:**
- The exact security requirements (depends on data sensitivity).
- The need for real-time vs. batch analytics (depends on use case selection).
- The extent of integration with external systems.

---

## 4. AI Collaboration Log

See AI_LOG.md for details.

---

## Submission Checklist
- [x] Forked the course organization repository
- [x] Created a working branch
- [x] Added deliverables
- [x] Reviewed submission for completeness and clarity
- [x] Prepared pull request with meaningful title and description

---

## Confirmation
I have reviewed my submission and confirm it meets the assignment requirements.
