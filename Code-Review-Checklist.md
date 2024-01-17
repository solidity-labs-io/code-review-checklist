# Code Review Checklist

This checklist is a set of steps that facilitates an in-depth and systematic review of smart contract code changes. It's designed to ensure a thorough understanding of the code, its connections with other systems, and its potential issues. This should be used by the code author and reviewer to ensure that the code is secure and functions as intended. Question all of your assumptions as the code author.

## Checklist

1. **Meeting kickoff**: The code author should provide context on software architecture.
2. **Review of fixes from the previous session**: Explain the underlying issues and their solutions if previous sessions have discovered vulnerabilities or issues.
3. **Review of changes since the last review**: Discuss each module's dependencies and changes.
4. **Line-by-line walk-through**: Go through each variable and function, stating assumptions on expected system behavior, and identify which users or actors can manipulate which values.
5. **Review of external calls**: Ensure that all external calls function as intended and are secured against potential threats.
6. **Review of variable and function visibility**: Ensure that all functions that can be made external are, and that functions that can be private are.
7. **Checks Effects Interactions (CEI)**: Verify that all actions in the contract are ordered correctly: checks, effects, and then interactions.
8. **Assert Protocol Invariants After State Changes ([FREI-PI](https://www.nascent.xyz/idea/youre-writing-require-statements-wrong))**: Verify that after any state changing function, the key protocol invariants remain intact.
9. **Rounding in the protocol's favor**: Confirm that any rounding errors favor the protocol and don't create vulnerabilities.
10. **Access Control Issues**: Review modifiers and question all assumptions around access control. Giving permissions to as few actors as possible.
11. **Front running**: Analyze potential front-running risks and vulnerabilities.
12. **Assumptions around unchecked or other gas optimizations**: Discuss any assumptions made regarding gas optimizations, particularly those left unchecked.
13. **Code and Architecture Quality**: Review the code and architecture quality, including separation of concerns, trust assumptions, comments, and documentation.
14. **Test Quality**: Review the test coverage and make sure unit tests coverage is 100%, and that integration tests cover the scenarios exactly as the system would be deployed in production. Low test coverage is a sign that a team is early in the SDLC.
15. **Review of slither run**: If uncertain about any finding’s severity, perform and review a slither run.
16. **Documentation of findings**: Record findings in an internal [audit log](Audit-Log-Template.md) on the PR. This helps document changes over time serves as a reference point for future audits and contributors to understand a projects security posture and architectural decisions that were made over time.

Remember, following this checklist diligently helps to enhance the internal security posture. However, it's not a substitute for a full audit, which is a comprehensive and examination of the entire codebase by external security researchers. The combination of vigilant internal security posture and thorough external audits are the keys to a more secure system.

## Recommended Additional Checklists
- [Simple Security Toolkit](https://github.com/nascentxyz/simple-security-toolkit/blob/main/audit-readiness-checklist.md)
- [Solcurity](https://github.com/transmissions11/solcurity)
- [Security Stack Part 1](https://medium.com/@elliotfriedman3/a-security-stack-4aedd8617e8b)
- [Security Stack Part 2](https://medium.com/@elliotfriedman3/a-security-stack-part-2-aaacbbf77346)