## PART 1: STRATEGIC PRINCIPLES (50)
>> Principles are worthless without action. Pick three from the entire list — one strategic, one psychological, one professional — and implement them from now. Then pick three more. The list is a map. You have to walk the path.

>> ***`Checks`*** >  ***`Effects`*** > ***`Interactions`***

>> Understand the *business logic* and find *invariant violations*. Focus less on syntax errors and more on broken assumptions.

>> "Don't read docs cover-to-cover. Focus on EVM, Gas, Token Standards, and Advanced sections (Bridges, Oracles, Scaling)."


### Targeting & Selection — How to Choose Where to Hunt
> ***1. Follow total value locked (TVL), not hype*** - A protocol with $1 billion TVL but low Twitter engagement is better than a trending protocol with $10 million. TVL directly correlates with bounty size and team urgency. Hype attracts hunters; TVL attracts payouts.

> ***2. Prioritize protocols with multiple integrations*** - When a primitive (like an oracle or swap router) is used by 50 downstream protocols, a single bug becomes 50 payouts. You're not just hunting one bug; you're hunting leverage.

> ***3. Attack the edges, not the core*** - Core trading or lending logic gets audited by four different firms. But the fee distributor, the reward calculator, the migration helper, the timelock executor — those get one quick look. That's where bugs hide.

> ***4. Target protocols immediately after major upgrades*** - Teams are exhausted after a big release. Their documentation is outdated. Their tests don't cover the new paths. The changelog tells you exactly what they were worried about — go look at those specific functions.

> ***5. Look for copy-pasted code from unaudited sources*** - Many projects borrow code from GitHub with a "should be fine" attitude. If the source project never had an audit, that borrowed code is a blind spot. Check the commit history — if they copied from an unknown repo, dig there.

> ***6. Hunt where the team has turnover*** - When the original developers leave, new hires inherit assumptions they don't fully understand. They'll touch code carefully, break invariants accidentally, and introduce subtle bugs. Look for protocols that lost key engineers.

> ***7. Focus on admin functions first*** - One unrestricted `setImplementation()` or `withdrawFees()` or `updateOracle()` is often a critical finding. Teams hide these in plain sight, assuming "onlyOwner" is sufficient. Check if owner is a single EOA or a real multisig with delay.

> ***8. Study the economic model before reading code*** - You can't find what you don't understand. Map the value flow: who deposits, who withdraws, who earns fees, who loses in a crash. The most severe bugs violate economic assumptions, not coding standards.

> ***9. Target protocols that raised recently*** - Fresh funding creates pressure to launch quickly. Roadmaps promise features. Investors expect returns. That pressure leads to skipped edge cases, incomplete testing, and rushed deploys. Strike in the first month after a raise.

> ***10. Prioritize cross-chain deployments*** - The same Solidity code behaves differently on different chains. Block times vary (2 seconds on Polygon, 12 on Ethereum, 1 on Solana). Native token mechanics differ. Gas limits change. A safe assumption on Ethereum becomes an exploit on BNB Chain.

---

### Investigation Methodology — How to Look

> ***11. Start with the deploy script, not the contract*** - Most auditors open the main contract first. That's wrong. The deploy script shows you constructor arguments, initializer calls, and setup order. One wrong parameter or a front-runnable initialize() can be a critical finding in minutes.

> ***12. Map all external calls on paper*** - Every time the protocol calls another contract (transfer, approve, oracle query, delegatecall), control leaves your hands. Draw a diagram. Count each one. For each external call, ask: "What if this contract is malicious? What if it reverts? What if it returns wrong data?"

> ***13. Trace every state variable to every write*** - Pick each storage variable. Find every function that writes to it. If more than one function writes to the same variable, ask: "Can these writes happen in an unexpected order? Can they conflict? Is there a race condition?"

> ***14. Read the test suite thoroughly*** - Tests are a confession. They show exactly what the team thought to check. Look for missing test cases — happy paths are tested, sad paths are tested, but adversarial paths often aren't. Write down every scenario they didn't test.

> ***15. Look for functions with no test coverage*** - Run coverage analysis. Functions with 0% coverage are functions the team never verified. That doesn't mean they're vulnerable, but it means you're the first person to really look at them.

> ***16. Run static analyzers, then ignore half their warnings*** - Slither, Mythril, and Aderyn produce hundreds of false positives. Learn which categories actually produce bugs (unchecked return values, tx.origin usage, delegatecall to user-supplied address) and ignore the noise.

> ***17. Simulate the protocol with a single user*** - Many bugs only appear in isolation. Run through every action as one address: deposit, withdraw, claim rewards, migrate, upgrade. Does anything break when no one else is interacting?

> ***18. Then simulate with two adversarial users*** - Now add a second address. Can user A front-run user B? Can user B block user A? Can they collude to extract value? Interaction bugs are some of the highest severity.

> ***19. Review every TODO and FIXME comment*** - Developers write TODOs when they know something is incomplete. They write FIXME when they suspect a problem. These comments are treasure maps. Go to those lines and finish their thought — the bug is usually nearby.

> ***20. Check every require message for information leakage*** - Error strings like "insufficient balance: 100 < 200" or "only owner: 0x1234" leak state. An attacker can front-run based on that leaked information. If an error reveals a pending state change, that's an exploit path.

---

### Time & Resource Management — How to Not Burn Out

> ***21. Batch similar protocols together*** - If you're going to understand Uniswap V2 forks, review ten of them in one week. The patterns repeat, the differences become obvious, and you develop a mental library of what forks get wrong.

> ***22. Set a timer for initial surface mapping*** - Give yourself exactly 30 minutes to understand entry points, privileged roles, external dependencies, and value flow. If after 30 minutes you can't articulate three high-risk areas, move to the next protocol.

> ***23. Stop after three hours without a lead*** - Diminishing returns hit hard after three hours of no findings. Take a break, switch protocols, or sleep on it. Forcing yourself to find something leads to false positives and frustration.

> ***24. Keep a running list of "likely safe" areas*** - Document what you've checked and deemed low-risk. Knowing what not to re-check saves hours. Update this list every session.

> ***25. Work offline first*** - Close Discord, Slack, Twitter, Telegram, and email. Set your status to "deep work." The first two hours of any review should be distraction-free. Surface-level scanning is for later passes.

> ***26. Schedule reviews of old protocols you already know*** - Dependencies change. Solidity versions upgrade. New economic attacks emerge. A protocol you audited six months ago might have new vulnerabilities today without any code change.

> ***27. Spend 10% of your time building tools*** - Write a custom invariant checker. Automate a deployment script. Build a fuzzing harness. Every hour spent tooling saves ten hours later.

> ***28. Never audit the same code twice in one week*** - Your brain pattern-matches. You'll read what you expect to see, not what's actually there. Wait at least a week between passes, or have a different researcher review after you.

> ***29. Use the last hour of each session for documentation*** - Write down every partial lead, every suspicious pattern, every question you didn't answer. Tomorrow's you will have a head start. Without documentation, you start from zero each session.

> ***30. Treat each protocol as a learning investment*** - Even if you find zero bugs, you learned a new system, new patterns, new mistakes to look for elsewhere. That knowledge compounds. Every hour is tuition, not wasted time.

---

### Advanced Strategic Thinking — Beyond the Obvious

> ***31. Follow the money, not the code*** - A clever logic bug in an obscure function doesn't matter if no value flows through it. Focus on functions that move assets, change ownership, set fees, or update oracles. Code is implementation; money is the target.

> ***32. Attack initialization sequences*** - The gap between contract deployment and the first legitimate interaction is a unique window. Front-run the initialize() call. Deploy your own implementation before the team does. These are one-shot vulnerabilities that disappear forever after first use.

> ***33. Study upgrade patterns obsessively*** - Proxies (transparent, UUPS, beacon), diamonds, immutable references — each has unique failure modes. Storage collisions, function clashing, initialization races. Become the person who understands upgrade mechanics better than the teams using them.

> ***34. Target timelock interactions*** - Many protocols use timelocks for governance. A timelock delays execution by hours or days. That delay creates opportunities: front-run the execution, cancel it, or prepare state changes that will be invalid by the time it executes.

> ***35. Look for rounding in your favor*** - Financial protocols do division. Division truncates. Truncation can be exploited if you control the inputs. Small rounding errors compound over many transactions. Ask: "Who loses the remainder? Can I be that person every time?"

> ***36. Trace every modifier to its conclusion*** - Modifiers can revert, which is fine. But they can also modify state, make external calls, or skip checks based on conditions. Read the modifier as if it were a function. Don't assume it does only what its name suggests.

> ***37. Map storage layout manually*** - Solidity packs variables into 32-byte slots. Two variables in the same slot can interfere with each other if one is written and the other is read. Storage collisions are invisible to most analysis tools. Draw the slot map.

> ***38. Review every unchecked block*** - Unchecked math assumes overflow is impossible. But assumptions fail when inputs are adversarial. An unchecked block around a multiplication that seems safe might become unsafe under extreme values. Verify every assumption manually.

> ***39. Check assembly blocks twice*** - Solidity's safety features (bounds checking, overflow protection, reentrancy guards) don't apply inside assembly. Assembly code is raw EVM. A single mistake there breaks everything around it. Read assembly like a criminal investigation.

> ***40. Examine error handling in low-level calls*** - Low-level calls (call, delegatecall, staticcall) return a boolean success flag and no automatic revert. Most code checks the boolean, but some doesn't. Missing the check means ignoring failures. Silent failures are exploits waiting for the right condition.

---

### Competitive & Professional Strategy — How to Win Long-Term

> ***41. Specialize in one primitive deeply*** - Generalist hunters survive. Specialists dominate. Become the oracle person. Or the lending math person. Or the cross-chain bridge person. Teams will invite you privately because you understand their domain better than they do.

> ***42. Build a reputation before chasing payouts*** - Your first ten reports should be impeccable — even if they're low severity. Clear language, reproduction steps, proof of concept, remediation advice. Judges remember quality. Quality unlocks private programs.

> ***43. Network with other hunters, not just protocols*** - Other hunters are not your enemies. Share blind spots, discuss tricky patterns, review each other's findings before submission. A community of skilled peers raises everyone's game. Isolation limits growth.

> ***44. Be easy to work with*** - Judges and protocol teams are humans. They get hundreds of reports. Make yours a pleasure to read. Be respectful in comments. Respond quickly to questions. People remember ease of interaction and invite easy people back.

> ***45. Ask for feedback on rejected reports*** - When a report is rejected as invalid or duplicate, politely ask why. Most judges will explain. That explanation is free education. You'll learn the judge's threshold, the team's mental model, and your own blind spots.

> ***46. Start with smaller bounties to learn process*** - Don't chase $1 million bounties first. Find $1,000 bugs on smaller protocols. Learn the submission workflow, the dispute process, the payout timeline. Ten small wins teach more than zero big wins.

> ***47. Keep a public portfolio*** - A blog, a GitHub, a Mirror.xyz collection of write-ups. Three well-documented findings show more skill than fifty unsupported claims. Portfolios get you invited, hired, and trusted.

> ***48. Learn to triage your own findings*** - Not every bug is a bounty. Some are invalid, some are duplicates, some are too minor, some are out of scope. Learn to recognize these before you spend hours writing a report. Move on quickly.

> ***49. Diversify across platforms*** - Immunefi has the biggest payouts. Code4rena offers contest structure. Sherlock provides insurance-backed awards. HackerOne has private invites. Don't rely on one pipeline. Build multiple streams of opportunity.

> ***50. Define success beyond money*** - Money fluctuates. Mastery is permanent. If you measure success only by payout size, dry spells will destroy you. Measure by bugs understood, skills learned, patterns documented, and respect earned. Those compound.
