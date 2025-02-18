# Architecture Decision Record (ADR) Template

## ADR 15: Security Assessment

### Status
- DRAFT

### Context
Our system currently stores intellectual property that sets Certifiable Inc. ahead of our competitors and with a strong reputation with candidates and employers hiring candidates.
We need to ensure that our future solution provides property security to our intellectual property and candidate data.

### Decision

 -  Data in Transit Encrypted using oAuth
 -  Data at Rest is Encrpyted using AES on sensitive data
 -  Implement comprehensive Logging and Monitoring for tracability
 -  Perform a Threat Model against our system design, using Micrsoft STRIDE approach


### Alternatives Considered
[Document any alternative options that were considered and explain why they were not chosen. This helps to provide insight into the decision-making process.]

### References
[Include any relevant references, such as documentation, discussions, or related ADRs, that helped inform the decision.]

### Date
[Date of the decision]
