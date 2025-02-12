# Architecture Decision Record (ADR)

## ADR 01: Aptitude Test Grader

### Status

- ACCEPTED

### Context

The current process of grading short answer submissions for examinations is manually handled by an expert architect, which is time-consuming and resource-intensive. Automating this process using AI can increase efficiency, reduce response time to the candidate and allow the company to reduce overall costs. The company has a historical dataset of graded answers which can be leveraged to train or inform AI solutions.

### Decision

The decision is to implement an AI-based grading system using a small Large Language Model (LLM) supported by a Retrieval-Augmented Generation (RAG) pattern. This solution will use the historical answer dataset to retrieve relevant information, enhancing the accuracy and reliability of the grading process.

### Consequences

_Positive Consequences_:

- **Efficiency**: Automating the grading process will significantly reduce the time required to assess each submission, improving overall operational efficiency.
- **Resource Allocation**: Frees up expert resources for higher-value activities, such as designing further examination case studies and questions, or engaging in quality assurance.
- **Scalability**: The solution can handle a large number of submissions simultaneously, making it scalable to accommodate peak periods or increased examination volumes.

_Negative Consequences_:

- **Complexity**: Implementing a RAG pattern adds complexity to the architecture, requiring additional considerations for data retrieval and integration with the LLM.
- **Initial Setup and Maintenance**: The system requires initial configuration of retrieval mechanisms and ongoing maintenance to ensure the dataset remains current and comprehensive.
- **Cost**: Using any LLM can incur costs, particularly if relying on third-party services. However, a smaller LLM may be more cost-effective than larger models.

### Alternatives Considered

1. **Training a Custom ML Model on Historical Dataset**
  **Rationale**: Leverage existing historical data to train a model specifically tailored for grading tasks.
  **Reasons for Rejection**:
    - Requires significant data science resources to develop and maintain.
    - Model training and retraining can be time-consuming.
    - Custom models may not generalize well to new or slightly varied questions unless frequently updated.

2. **Using a Large LLM for Grading**
  **Rationale**: Utilize pre-trained capabilities of a large LLM to handle complex language understanding tasks directly.
  **Reasons for Rejection**:
    - High operational costs due to computational demands.
    - Potential overfitting or misinterpretation if not specifically fine-tuned for grading contexts.
    - Dependency on external providers for updates and fine-tuning which may not align with internal data privacy standards.

### References
[Include any relevant references, such as documentation, discussions, or related ADRs, that helped inform the decision.]

### Date
[Date of the decision]
