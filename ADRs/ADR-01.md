# Architecture Decision Record (ADR)

## ADR 01: Aptitude Test Grader

### Status

- ACCEPTED

### Context

The current process of grading short answer submissions for examinations is manually handled by an expert architect, which is time-consuming and resource-intensive. Automating this process using AI can increase efficiency, reduce response time to the candidate and allow the company to reduce overall costs. The company has a historical dataset of graded answers which can be leveraged to train or inform AI solutions.

### Decision

The decision is to implement an AI-based grading system using a small Large Language Model (LLM) supported by a Retrieval-Augmented Generation (RAG) pattern. This solution will use the historical answer dataset to retrieve relevant information, enhancing the accuracy and reliability of the grading process.

### Alternatives Considered

1. **Using a small LLM supported by RAG pattern**
  *Pros*:
    - Efficiency: Significantly reduces the time required to grade submissions.
    - Resource Allocation: Frees up expert resources for more strategic activities.
    - Scalability: Capable of handling large volumes of submissions simultaneously.
    - Cost-effectiveness: Smaller LLMs are generally more economical compared to larger models.
    - Availability of training data: We have a large historical dataset available to populate the RAG store.
  *Cons*:
    - Complexity: Increases architectural complexity with the integration of RAG.
    - Initial Setup and Maintenance: Requires effort to configure and maintain retrieval mechanisms.

2. **Training a Custom ML Model on Historical Dataset**
  *Pros*:
    - Tailored Solution: Custom model specifically trained for the grading task using historical data.
    - Control: Full control over the model training process and updates.
    - Availability of training data: We have a large historical dataset available to train the model.
  *Cons*:
    - Resource Intensive: Requires significant data science expertise and resources for development and maintenance.
    - Time-Consuming: Model training and frequent retraining needed to accommodate new data.
    - Generalization: Risk of poor performance on new or varied questions without regular updates.

3. **Using a Large LLM for Grading**
  *Pros*:
    - Advanced Capabilities: Leverages pre-trained language understanding for handling complex grading tasks.
    - Simplicity: Reduced need for extensive custom model training.
  *Cons*:
    - Cost: High operational costs due to computational demands of large models.
    - Overfitting Risk: May require fine-tuning to avoid misinterpretation of grading contexts.
    - Dependency: Relies on external service providers, which may not align with internal privacy and update needs.
  
4. **Using an Ensemble Approach with Specialized Models**
  *Pros*:
    - Specialized Insights: Different models can focus on distinct aspects of the grading, such as content accuracy, language use, and logical coherence, potentially providing a more nuanced evaluation.
    - Collaborative Grading: By aggregating impressions from multiple models, the system can arrive at a consensus grade, potentially improving grading reliability and fairness.
    - Adaptability: Models can be independently updated or replaced as grading criteria evolve or new requirements emerge.
  *Cons*:
    - Complex Coordination: Requires sophisticated algorithms to integrate and reconcile diverse model outputs into a single grade.
    - Resource Demand: Running multiple models simultaneously can increase computational requirements.
    - Integration Complexity: More complex architecture needed to manage and coordinate the outputs of various models effectively.

### References
[Include any relevant references, such as documentation, discussions, or related ADRs, that helped inform the decision.]

### Date
[Date of the decision]
