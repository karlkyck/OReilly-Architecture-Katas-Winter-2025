# Architecture Decision Record (ADR)

## ADR-13: Grader Output Validation

### Status
- ACCEPTED

### Context
The LLM-powered grading system aims to automate the assessment of short answers and architectural submissions, providing efficiency and scalability. However, ensuring the accuracy and reliability of the automatically generated grades is critical to maintain trust in the system. A robust validation strategy is required to verify the alignment of AI-generated grades with manual grading standards.

### Decision
The decision is to have Expert Architects validate a random sample of automatically graded tests. This approach involves selecting a small percentage of submissions to be reviewed manually, comparing AI-generated grades with expert assessments to ensure accuracy. Statistical analysis of grading may be something we want to explore as a further validation or benchmarking of our AI-grading systems.

### Alternatives Considered

#### 1. Manual validation of a small percentage of AI-graded submissions

*Description*:

Leverage the capacity and expertise of our Expert Architects to manually grade a small subset of AI-graded submissions. These should be graded blind, without knowledge of the AI-provided grading. Following assignment of a manual grade by the Expert Architect, they should be presented with the AI-generated grade and given the opportunity to compare both and flag for further analysis if large variation is noticed.

*Pros*:
- Accuracy Assurance: Provides a direct comparison between AI and human grading, helping to identify discrepancies.
- Quality Control: Regular expert reviews maintain grading quality and detect potential issues in the grading model.
- Continuous Improvement: Feedback from expert reviews can be used to refine and improve the AI model over time.

*Cons*:
- Resource Intensity: Requires time and expertise from architects, although only for a small sample.
- Potential Bias: Expert reviews may introduce bias if not randomly selected or if review criteria are not standardized.
- Scalability: The approach might become challenging to scale if the volume of graded tests significantly increases. However, maintaining a statistically significant amount should be achievable with an ever decreasing percentage of tests reviewed as overall volume increases.

#### 2. Full Parallel Grading by Experts

*Description*:

Use Expert Architects to grade tests in parallel with AI capabiliies. Has potential for initial validation of models, but not a feasible or sustainable approach go-forwards.

*Pros*:
- Comprehensive Validation: Every AI-graded test is compared to expert assessments, ensuring maximum accuracy.
- Immediate Feedback: Provides immediate insights into any grading discrepancies.

*Cons*:
- Highly Resource-Intensive: Not feasible due to the need for extensive time and resources.
- Costly: Significant increase in operational costs to maintain parallel grading efforts. Negates any savings realised by introducing AI capabilities.

#### 3. Statistical Analysis of Grading Trends

*Description*:

Leverage the historical dataset available to perform statistical analysis and determine if the distribution of scores from our AI-grader is consistent with manual grading.

*Pros*:
- Data-Driven Insights: Uses statistical methods to analyze grading consistency and trends over time.
- Scalable: Can easily handle large volumes of data without manual effort.

*Cons*:
- Indirect Validation: May not catch specific discrepancies or errors in individual submissions.
- Complexity: Requires expertise in statistical analysis and model evaluation techniques.

#### 4. Automated Cross-Validation Techniques

*Description*:

Systematically evaluate and validate the accuracy and consistency of the AI grading model. This involves dividing the dataset into multiple partitions, typically known as "folds." The model is trained on a subset of these folds and validated on the remaining fold. This process is repeated multiple times with different partitions to provide a robust evaluation.

*Pros*:
- Efficiency: Uses automated processes to assess grading accuracy based on predefined metrics or benchmarks.
- Consistency: Provides consistent validation without human error.

*Cons*:
- Lack of Nuance: Automated methods may miss context-specific discrepancies that human experts could catch.
- Initial Setup Complexity: Requires development of robust validation algorithms and metrics.

### References
[Include any relevant references, such as documentation, discussions, or related ADRs, that helped inform the decision.]

### Date
[Date of the decision]
