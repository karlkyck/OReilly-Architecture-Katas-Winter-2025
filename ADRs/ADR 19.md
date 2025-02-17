# Architecture Decision Record (ADR)

## ADR 19: Architectural Submission Grader

### Status

- ACCEPTED

### Context

The current grading system for architectural submissions requires an automated solution that can handle complex assessments while providing detailed feedback. A single AI model may struggle to capture all the nuances of a submission across multiple criteria. Therefore, an approach that leverages specialized AI capabilities is desirable. Additionally, cost efficiency remains a key concern, necessitating a solution that optimizes resource usage.

### Decision

The decision is to implement a Retrieval-Augmented Generation (RAG) based ensemble system. This involves using multiple AI personas, each tasked with grading a specific aspect of the submission. The system will parse submissions to extract key features, tailoring the context for each LLM to reduce costs.

### Alternatives Considered

#### 1. RAG-Based Ensemble System with Specialized AI Personas

*Description*:

This approach utilizes multiple AI personas, each powered by a Large Language Model (LLM) to grade distinct aspects of the architectural submission, such as design, functionality, and compliance with standards. The system uses a RAG framework to provide relevant information to each persona. By parsing the submission to extract key features, the context for each LLM is narrowed, thus optimizing performance and controlling costs.

*Pros*:
- Specialization: Allows each LLM to focus on a specific grading aspect, improving accuracy and depth of feedback.
- Cost Efficiency: By narrowing context, the system reduces the computational load and associated costs for each grading task.

*Cons*:
- Complex System Integration: Requires sophisticated architecture to manage multiple AI personas and integrate their outputs.
- Coordination Overhead: Needs careful coordination to ensure consistent and coherent final grading outcomes.

#### 2. Single Comprehensive LLM

*Description*:

A single, large LLM would be employed to handle all grading tasks, leveraging its extensive pre-trained capabilities to assess various aspects of the submission.

*Pros*:
- Simplicity: Easier to manage a single model as opposed to coordinating multiple personas.
- Unified Approach: Ensures consistency in grading style and feedback delivery.

*Cons*:
- Cost: Higher operational costs due to the need for a powerful, comprehensive model.
- Performance Limitations: A single model may struggle to capture nuanced details across different grading criteria.

#### 3. Traditional Rule-Based System

*Description*:

A rule-based system would be used, incorporating predefined criteria and guidelines to automate grading.

*Pros*:
- Predictability: Offers predictable outcomes based on predefined rules and logic.
- Lower Development Costs: Initial setup might be simpler than training and deploying multiple LLMs.

*Cons*:
- Inflexibility: Lacks adaptability and may not effectively handle complex or creative submissions.
- Maintenance: Requires continuous updates to keep rules current with evolving standards and criteria.
