# Architecture Decision Record (ADR) Template

## ADR 15: Privacy Assessment

### Status
- DRAFT

### Context
Our system currently stores details of employees of Certifiable Inc. and a large number of Candidates (Customers). This is going to move to several new legal jurisdictions globally.
We need to ensure that our future solution provides those impacted with the relevent information regarding their personal data and that all their data is not accessible by others.
Using AI models introduces an additional consideration, especially if we use AI on personally identifable data.

### Decision

Perform a Privacy Impact Assessment

Data Privacy - Anonymization where appropriate 
Data Governance - laws and regulations for each jurisdiction
Data integrity - 
Data Storage and Transmission - 
Data Rentention and Disposal - How long do we retain failed (and passed) test data and feedback
Audits - 

### Alternatives Considered
[Document any alternative options that were considered and explain why they were not chosen. This helps to provide insight into the decision-making process.]

### References
[Include any relevant references, such as documentation, discussions, or related ADRs, that helped inform the decision.]

### Date
[Date of the decision]
