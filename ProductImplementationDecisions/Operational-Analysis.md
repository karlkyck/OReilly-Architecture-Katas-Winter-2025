
# Operational Analysis: Ensuring Operational Efficiency and Profitability

### Status
- ACCEPTED

### Context
Certifiable, Inc. is preparing for significant scaling, with the potential to grow by more than 10 times. The income per certification remains at $800. As we aim to maintain our Service Level Agreements (SLAs) for test completion amidst this growth, it's crucial to assess our current grading capacity expert resources and profit margins.

**Current Situation Analysis**
- **Current Number of Scoring Experts**: 300
- **Current Weekly Candidates**: 200
- **Current Income from Certification Exams**: $160,000
- **Current Architecture Expert Hourly Rate**: $50
- **Current Certification Income**: $800
- **Grading Time for Tests**:
  - Test 1 (Aptitude): 3 hours per candidate
  - Test 2 (Architecture Submission): 8 hours per candidate
  - **Total Grading Time per Candidate**: 11 hours
  - **Total Grading Cost**: $550
  - **Total Profit per candidate (Per-Operating Cost)**: $250


**Current Weekly Grading Capacity**
- **Total Weekly Hours Available per Expert**: 40
- **Total Weekly Hours Available for All Experts**: 12,000
- **Total Candidates That Can Be Graded per Week**: Approximately 1,090

### Projected Growth Scenarios
#### 1. 5x Growth Scenario
- **Projected Weekly Candidates**: 1,000
- **Total Grading Time Required**: 11,000 hours
- **Current Capacity**: 12,000 hours (sufficient to meet 5x growth)
- **Implication**: No immediate need for additional scoring experts under this scenario.

#### 2. 10x Growth Scenario
- **Projected Weekly Candidates**: 2,000
- **Total Grading Time Required**: 22,000 hours
- **Current Capacity**: 12,000 hours (**not sufficient to meet 10x growth**)
- **Deficit**: 10,000 hours
- **Additional Experts Needed**: 250 (Total Experts Required: 550)

### Financial Implications
- **Weekly Income with 2,000 Candidates**: $1,600,000
- **Net Profit from Certification**: $1,100,000

| Weekly Candidates | Total Grading Time Required (hours) | Experts Needed |
|-------------------|-------------------------------------|----------------|
| 200               | 2,200                               | 55             |
| 300               | 3,300                               | 83             |
| 400               | 4,400                               | 110            |
| 500               | 5,500                               | 138            |
| 600               | 6,600                               | 165            |
| 700               | 7,700                               | 193            |
| 800               | 8,800                               | 220            |
| 900               | 9,900                               | 248            |
| 1,000             | 11,000                              | 275            |
| 1,100             | 12,100                              | 303            |
| 1,200             | 13,200                              | 330            |
| 1,300             | 14,300                              | 358            |
| 1,400             | 15,400                              | 385            |
| 1,500             | 16,500                              | 413            |
| 1,600             | 17,600                              | 440            |
| 1,700             | 18,700                              | 468            |
| 1,800             | 19,800                              | 495            |
| 1,900             | 20,900                              | 523            |
| 2,000             | 22,000                              | 550            |

![Experts Needed](../Kata-Experts-Needed.png)

### SLA Improvement
Enhancing operational efficiency presents an opportunity to reduce lead times for assessments and feedback, thereby increasing candidate satisfaction and improving competitive positioning.


### AI Enabled Assessment Impact
- **Current Architecture Expert Hourly Rate**: $50
- **Current Certification Income**: $800
- **Grading Time for Tests - Manual**:
  - Test 1 (Aptitude): 3 hours per candidate
  - Test 2 (Architecture Submission): 8 hours per candidate
  - **Total Grading Time per Candidate**: 11 hours
  - **Test 1 cost per grading**: $150
  - **Test 2 cost per grading**: $400
  - **Total Grading Cost**: $550
  - **Total Profit per candidate (Per-Operating Cost)**: $250

- **Current Certification Income**: $800
- **Grading Time for Tests - AI**:
  - **Test 1 cost per grading - AI** (Assumpation 20 Short Questions): $0.13
  - **Test 2 cost per grading - AI**: (Assumptions: 10 Architectural Personas, 50k Tokens per Persona. Lama3.2..) 
  - **Total Grading Cost**: $
  - **Total Profit per candidate (Per-Operating Cost)**: $


Financial impact:

[Azure / OpenAI Model Pricing](https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/)

[AWS Bedrock Pricing](https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/)


SLA Impact:

### Proposed Decision
- **Implement AI**: Explore the use of AI technology to manage grading processes, enabling us to meet increased demand without hiring additional experts.

### Alternatives Considered
- **Hiring Additional Experts**: Weighing the feasibility of scaling and managing 250 additional experts against potential efficiency improvements.
- **Implementing AI-Assisted Grading**: Assessing investment in AI tools to reduce reliance on human experts while increasing grading efficiency.
- **Exploring Alternative Revenue Streams**: Evaluating opportunities such as additional training programs or consulting services.
- **Monitoring Market Trends**: Continuously analyzing certification demand to adjust hiring strategies accordingly.

### Date
- **Decision Date**: 2025-02-18
