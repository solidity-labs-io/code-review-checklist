# Code Review Checklist

Before we dive into the checklist, it's crucial to understand its role and how to use it effectively. This checklist is a set of steps that facilitates an in-depth and systematic review of smart contract code changes. It's designed to ensure a thorough understanding of the code, its connections with other systems, and its potential issues.

## Checklist

1. **Meeting kickoff**: The code author should provide context on software architecture.
2. **Review of fixes from the previous session**: Explain the underlying issues and their solutions if previous sessions have discovered vulnerabilities or issues.
3. **Review of changes since the last review**: Discuss each module's dependencies and changes.
4. **Line-by-line walk-through**: Go through each variable and function, stating assumptions on expected system behavior, and identify which users or actors can manipulate which values.
5. **Review of external calls**: Ensure that all external calls function as intended and are secured against potential threats.
6. **Checks Effects Interactions (CEI)**: Verify that all actions in the contract are ordered correctly: checks, effects, and then interactions.
7. **Rounding in the protocol's favor**: Confirm that any rounding errors favor the protocol and don't create vulnerabilities.
8. **Access Control Issues**: Review modifiers and question all assumptions around access control. Giving permissions to as few actors as possible.
9. **Front running**: Analyze potential front-running risks and vulnerabilities.
10. **Assumptions around unchecked or other gas optimizations**: Discuss any assumptions made regarding gas optimizations, particularly those left unchecked.
11. **Review of a slither run**: If uncertain about any finding’s severity, perform and review a slither run.
12. **Documentation of findings**: Record findings in an internal audit log on the PR. This helps document changes over time serves as a reference point for future audits and contributors to understand a projects security posture and architectural decisions that were made over time.

Remember, following this checklist diligently helps to enhance the internal security posture. However, it's not a substitute for a full audit, which is a comprehensive and systematic examination of the entire codebase by external security researchers. The combination of vigilant internal security posture and a thorough external audit is the key to a robust and secure system.

## Recommended Additional Checklists
- [Simple Security Toolkit](https://github.com/nascentxyz/simple-security-toolkit/blob/main/audit-readiness-checklist.md)
- [Solcurity](https://github.com/transmissions11/solcurity)
