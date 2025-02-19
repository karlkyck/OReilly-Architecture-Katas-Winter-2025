# Architecture Characteristics

Architecture characteristics, often referred to as quality attributes (ilities) or non-functional requirements, define the properties of an architecture to meet the technical and business goals.

## Define needed characteristics

Starting from the business requirements the following important characteristics were deemed as relevant for the SoftArchCert product:

| **Term**             | **Definition**                                                                                                                                                                                                                                                                                                                             |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **cost**             | Taking into account cost implications early and continuously throughout the design, implementation, and ongoing maintainance of the system from a total cost of ownership (TCO) perspective including development, operational, maintenance & support, training, infrastructure, compliance & regulatory, time-to-market, and risks costs. |
| **scalability**      | A function of system capacity and growth over time; as the number of users or requests increase in the system, responsiveness, performance, and error rates remain constant                                                                                                                                                                |
| **accuracy**         | Accuracy and precision is used to characterize and measure results of an AI process that results in the transformation of data, information, knowledge, or wisdom to a higher-valued form.                                                                                                                                                 |
| **availability**     | The amount of uptime of a system; usually measured in 9's (e.g., 99.9%)                                                                                                                                                                                                                                                                    |
| **testability**      | The ease of and completeness of testing                                                                                                                                                                                                                                                                                                    |
| **data integrity**   | The data across the system is correct and there is no data loss in the system                                                                                                                                                                                                                                                              |
| **data consistency** | The data across the system is in sync and consistent across databases and tables                                                                                                                                                                                                                                                           |
| **fault tolerance**  | When fatal errors occur, other parts of the system continue to function                                                                                                                                                                                                                                                                    |
| **auditability**     | Tracking, logging, and providing evidence of operations, decisions, and changes to data over time. This ensures that the system's activities can be reviewed and verified for accuracy, compliance, and security.                                                                                                                          |
| **sustainability**   | ability to maintain long-term operation, adaptability, and efficiency while minimizing negative impacts on the environment, resources, and social aspects                                                                                                                                                                                  |
| **feasibility**      | Taking into account timeframes, budgets, and developer skills when making architectural choices; tight timeframes and budgets make this a driving architectural characteristic                                                                                                                                                             |
| **security**         | The ability of the system to restrict access to sensitive information or functionality                                                                                                                                                                                                                                                     |
| **observability**    | The ability of a system or a service to make available and stream metrics such as overall health, uptime, response times, performance, etc.                                                                                                                                                                                                |

## Choosing the driving characteristics

Key characteristics prioritized:

- **Cost**: Essential, as the cost of implementing and operating the system using AI technologies to automatically grade tests must be signficantly lower than the cost to manually grade tests especially at scale.
- **Scalability**: A scalable system is required to handle the expected increase from 200 candidates per week to 5-10X based on oversees expansion as well as the anticipated 21% growth over the next 4 years.
- **Accuracy**: Accuracy of the certification process is vital for the success of the company, and critical to ensure candidates do not suffer job loss or career damage due to inaccuracy.
- **Reliability**: In addition to the reliability the existing system exhibits.
  - **Availability**: The system remains up and servicing requests as the certification process is essential for candidates to become certified or renew certification for the purposes of their employment and career.
  - **Testability**: Robust regression tests are needed for non-deterministic AI systems to ensure quality and accuracy.
  - **Data Integrity**: Data generated by AI systems if not stored correctly with without data loss would be detrimental to the certification process.
  - **Data Consistency**: Data generated by AI systems if not in sync and consistent across databases and tables would be detrimental to the certification process.
  - **Fault Tolerance**: Ensures product stability and partial functional availability in the system in the event of component failure.
- **Auditability**: AI systems processes and results can be reviewed and verified for accuracy, compliance, and security.
- **Sustainability**: Workloads, especially AI workloads, use the least amount of energy, cooling, embodied carbon, and carbon emissions possible while serving customer needs.
- **Feasibility**: Cost-effective decisions minimize variance in basic functionality costs, offsetting the uncertainty of AI integration and maintenance.
- **Security**: Essential, as candidate details are stored in the system, along with the entire history of candidate answers to questions, and the examination questions both current and past.
- **Observability**: It is crucial to provide the right level of system observability so errors can be detected early, root cause established and dealt with quickly, and decisions to deploy a temporary increase in manual grading made when needed to keep the grading backlog at manageable levels.

Reduced priorities:

- **Integrity**: This is covered by accuracy, reliability, and auditability,

## Selecting the Top 3

During the requirements gathering process and the [EventStorming](../Event%20Storming/event-storming.md) session, we identified four main challenges:

- We need to carefully balance cost and accuracy whilst meeting scaling targets without having to scale personell linearly with demand.
- GenAI is non-deterministic, so we need a way to continually test, monitor, and calibrate the automatic graders.
- We need to be able to satisfactorily explain the process of how the automatic graders determined their score and provided feedback for the purposes of optimisation, and potential external litigation.
- To keep SoftArchCert's continuing competitive advantage we need to ensure the solution can continuously evolve to meet tighter SLAs and customer demands whilst maintaining accuracy and reliability.

These challenges led us to conclude that _Cost_, _Scalability_, and _Accuracy_ are the top three driving factors for this project.

### Cost

- We are using a baseline average cost per manual Aptitude Test grading and manual Architecture Submission grading to compare our GenAI solution to.
- A low cost GenAI model will provide basic inferencing capabilities with the expert software architecture knowledge relevant to queries being supplied by the RAG pattern.
- AWS Bedrock inference batching allows us to spread queries out over time, while still meeting SLAs, and allows us to avail of 50% lower price compared to on-demand inference pricing using AWS Bedrock.
- To future-proof the SoftArchCert system, we aim to ensure the interchangeability of GenAI models so we can continue to leverage advancements in performance, speed, accuracy, and cost to improve SLAs and customer satisfaction.

### Scalability

- Currently 200 candidates are graded per week in the US which is expected to grow to 5-10X based on oversees expansion as well as the anticipated 21% growth over the next 4 years.
- AWS Step Functions allow us to orchestrate grading queries to AWS Bedrock, and AWS Bedrock Knowledge Bases to facilitate the RAG pattern. These capabiliies are highly scalable and able to meet the expected demand.
- The automatic Aptitude Testing grader will have higher demand, but lower processing needs compared to automatic Architecture Submission grader which will lower load, but higher processing needs.

### Accuracy

- Inaccurate grading can result in a candidate not getting or maintaining a job and can impact a candidate's career.
- Inaccurate or misleading certification exams and case studies can undermine the credibility of the company’s current standing in the marketplace, so accuracy of the certification process is vital for the success of the company.
- Robust regression tests are needed for non-deterministic AI systems to ensure quality.
- Continuous calibration of the results from AI processes against a small sample of equivalent manual processing ensures accuracy remains high.
