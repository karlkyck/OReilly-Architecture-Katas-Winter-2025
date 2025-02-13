# Architecture Decision Record (ADR)

## ADR 15: Using AI to generate Architecture questions for the exam

### Status
- PROPOSED

### Context
We are exploring opportunities to integrate Generative AI into the certification process. One critical aspect is the creation 
of high-quality examination questions that assess candidates’ knowledge and skills in software architecture. Automating 
the generation of these questions using AI can enhance scalability, reduce the manual workload on experts, and ensure a 
diverse and updated question pool that reflects current industry standards.

### Decision
To implement an AI-based approach for generating architecture exam questions, we will proceed with the following plan:

- Integration of Generative AI Models:
Utilize advanced Generative AI models to create a wide variety of architecture-related questions. This approach will 
leverage existing databases of architectural concepts, best practices, and industry standards to produce relevant and 
challenging questions.

- Training and Fine-Tuning:
Fine-tune the chosen AI model on a curated dataset comprising previously used questions, curriculum standards, and expert 
feedback. This will help ensure that the AI-generated questions meet the quality standards expected from the certification 
process.

- Dynamic Question Generation:
Enable the AI system to generate questions dynamically based on various parameters such as difficulty level, topic 
coverage, and current trends in software architecture. This flexibility will ensure that the examination remains relevant 
and comprehensive.

- Expert Review Mechanism:
Establish a review process where expert software architects evaluate AI-generated questions for clarity, accuracy, and 
relevance. This step will help maintain the integrity of the examination process and ensure that all questions adhere to 
consistently high standards.

- Feedback Loop for Continuous Improvement:
Create a mechanism to collect feedback on the effectiveness of AI-generated questions from both candidates and experts. 
This feedback will inform further iterations and improvements of the AI model, ensuring that it evolves based on real-world 
performance.

### Alternatives Considered
- **Option 1:** Manual Question Creation:
Continuing to rely solely on expert architects for question generation was considered. However, this approach is not 
scalable and does not efficiently meet the projected demand. The manual process can be time-consuming and may lead to a 
static question pool.

- **Option 2:** Static Question Bank:
Using a static question bank that has not been updated was an alternative. This option risks producing outdated content 
and may not adequately assess the evolving landscape of software architecture, reducing the effectiveness of the certification.

- **Option 3:** Hybrid Approach with Limited AI Use:
A hybrid model where AI aids experts but does not generate full questions was also evaluated. While this could enhance 
efficiency, it may not fully leverage the capabilities of Generative AI to provide diverse and comprehensive question 
coverage.

### References

### Date
02/13/2025
