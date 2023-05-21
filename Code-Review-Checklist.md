# Code Review Checklist

Before we dive into the checklist, it's crucial to understand its role and how to use it effectively. This checklist is a tool that facilitates an in-depth and systematic review of smart contract code. It's designed to ensure a thorough understanding of the code, its connections with other systems, and its potential issues. By following this checklist during a review meeting, the team can minimize oversights, and all potential bugs are identified.

The checklist consists of a series of steps and considerations that provide a comprehensive review of the code's functionality, efficiency, and security. Each item should be diligently reviewed and discussed with the team, leading to a consensus before moving on to the next. The purpose is not merely to complete the checklist, but to gain a holistic understanding of the code and its potential implications. Following this approach will ensure that the review process is not just a formality, but a valuable step in the development process.

## Checklist

1. **Meeting kickoff**: The code author should provide context on software architecture.
2. **Review of fixes from the previous session**: Explain the underlying issues and their solutions.
3. **Review of changes since the last review**: Discuss each module's dependencies and changes.
4. **Line-by-line walk-through**: Go through each variable and function, stating assumptions on expected system behavior, and identify who can manipulate which values.
5. **Review of external calls**: Ensure that all external calls function as intended and are secured against potential threats.
6. **Checks Effects Interactions (CEI)**: Verify that all actions in the contract are ordered correctly: checks, effects, and then interactions.
7. **Rounding in the protocol's favor**: Confirm that any rounding errors favor the protocol and don't create vulnerabilities.
8. **Access Control Issues**: Review modifiers and question all assumptions around access control.
9. **Front running**: Analyze potential front-running risks.
10. **Assumptions around unchecked or other gas optimizations**: Discuss any assumptions made regarding gas optimizations, particularly those left unchecked.
11. **Review of a slither run**: If uncertain about any finding’s severity, perform and review a slither run.
12. **Documentation of findings**: Record findings in an internal audit log on the PR.

Remember, following this checklist diligently helps to enhance the internal security posture. However, it's not a substitute for a full audit, which is a comprehensive and systematic examination of the entire codebase by external auditors. The combination of vigilant internal security posture and a thorough external audit is the key to a robust and secure system.
