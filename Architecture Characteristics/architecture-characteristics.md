# Architecture Characteristics

Architecture characteristics, often referred to as quality attributes (ilities) or non-functional requirements, define the properties of an architecture to meet the technical and business goals.

## Define needed characteristics

Starting from the business requirements the following important characteristics were deemed as relevant for the SoftArchCert product:

| **Term**             | **Definition**                                                                                                                                                                                                                                                                                                                             |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **cost**             | Taking into account cost implications early and continuously throughout the design, implementation, and ongoing maintainance of the system from a total cost of ownership (TCO) perspective including development, operational, maintenance & support, training, infrastructure, compliance & regulatory, time-to-market, and risks costs. |
| **scalability**      | A function of system capacity and growth over time; as the number of users or requests increase in the system, responsiveness, performance, and error rates remain constant                                                                                                                                                                |
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
- **Reliability**:
  - **Availability**: As a recognized leader in certification, accuracy of tests, case studies, and grading it is essential that the system remains in operational as significant downtime can result in negative impacts to reputation, market share, and a candidate getting or maintaining a job due to system outage and a backlog of pending test gradings.
  - **Testability**: Robust regression tests are needed for non-deterministic AI systems to ensure quality and accuracy, with parallel test runs to ensure no significant deviations in grading accuracy from previous releases.
  - **Data Integrity**:
  - **Data Consistency**:
  - **Fault Tolerance**: Ensures product stability, grading is taking place for the Aptitude Test or Architecture Submission either automatically or manually, and SLAs are being met even if parts of the system experiences downtime.
- **Auditability**: It is critical that automatic grading processes and results are auditable in the case of litigation for a Certification Program where the company's reputation, and the livelihood of candidates may be effected due to inaccuracies.
- **Sustainability**: It is increasingly import that the system is optimised for energy, water, and infrastructure usage, especially power and water coolant demanding GenAI systems.
- **Feasibility**: Cost-effective decisions minimize variance in basic functionality costs, offsetting the uncertainty of AI integration and maintenance.
- **Security**: Essential, as candidate details are stored in the system, along with the entire history of candidate answers to questions, and the examination questions both current and past.
- **Observability**: It is crucial to provide the right level of system observability so errors can be detected early, root cause established and dealt with quickly, and decisions to deploy a temporary increase in manual grading made when needed to keep the grading backlog at manageable levels.

Reduced priorities:

- **Integrity**: This is covered by reliability and auditability,
- **Reliability**: Ensuring that SLAs are met; data is correct and consistent across systems such that automatic grading, scoring, and feeback are accurate; manual grading is available in the case of system outage, automatic grading results in low confidence scoring & feedback, and continuous calibration against a constant random sampling of Aptitude tests and Architecture Submissions.
- **Auditability**: Ensuring that the processes and results of automatic grading can be audited and details provided when queries are made.

## Selecting the Top 3

During the requirements gathering process and the [EventStorming](/EventStorming/event-storming.md) session, we identified four main challenges:

- We need to carefully balance cost and accuracy whilst meeting scaling targets without having to scale personell linearly with demand.
- GenAI is non-deterministic, so we need a way to continually test, monitor, and calibrate the automatic graders.
- We need to be able to satisfactorily explain the process of how the automatic graders determined their score and provided feedback for the purposes of optimisation, and potential external litigation.
- To keep SoftArchCert's continuing competitive advantage we need to ensure the solution can continuously evolve to meet tighter SLAs and customer demands whilst maintaining accuracy and reliability.

These challenges led us to conclude that _Cost_, _Scalability_, and _Reliability_ are the top three driving factors for this project.

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

### Reliability

#### Availability

- System up time is a competitive advantage directly impacting company reputation and customer satisfaction as candidate employment and careers hinge on certification.

#### Testability

- Maintaining a high degree of accuracy in grading scores and feedback is critical to maintaining the reputation and competitive advantage of the company.
- Continuous calibration of the automatic graders against manual grading and historical grading will be necessary to maintain accuracy.
- Leveraging newer more cost effective GenAI models necessitates continous regression testing.

#### Data Integrity

#### Data Consistency

#### Fault Tolerance

-
