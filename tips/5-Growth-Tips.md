
# PART 5: LEARNING & GROWTH PRINCIPLES (25)

## Knowledge Acquisition

> ***126. Learn the EVM from the bottom up*** - Stack, memory, storage, calldata, opcodes, gas costs. You cannot defend what you don't understand at machine level. Solidity is a veneer. The EVM is the truth.

> ***127. Read every CVE in your target space*** - MakerDAO vulnerabilities. Compound. Uniswap. Curve. Every public disclosure is a free masterclass. Read the report, then read the patch, then understand why the patch works.

> ***128. Re-simulate historical exploits*** - Take a past exploit transaction. Replay it locally. Understand each opcode. Change one parameter and see what breaks. You'll learn more in one replay than ten theory readings.

> ***129. Study non-EVM vulnerabilities*** - CosmWasm bugs. Solana programs. Bitcoin script edge cases. Cross-domain knowledge sparks novel approaches. The best Ethereum hunters sometimes borrow from other chains.

> ***130. Learn formal verification basics*** - You don't need to become a theorem prover. But understanding invariants, pre/post conditions, and loop invariants changes how you read code. Certora, Halmos, and Foundry invariants are entry points.

---

## Skill Building

> ***131. Practice on deliberately vulnerable code*** - Ethernaut. Damn Vulnerable DeFi. Secureum CTF. These are gyms for your skills. Solve each level without looking at solutions. Then solve it again differently.

> ***132. Participate in contests as a learner, not a earner*** - Join Code4rena or Sherlock with zero expectation of winning. Focus on understanding the codebase and submitting one good finding. Pressure to earn kills learning.

> ***133. Review other hunters' write-ups*** - How did they structure their report? What evidence did they include? How did they prove severity? Treat good write-ups as templates for your own.

> ***134. Build a personal library of patterns*** - Category: reentrancy variants. Category: oracle manipulation. Category: access control misses. Category: initialization races. Add to it every time you see something new.

> ***135. Write a finding every week, even if small*** - Don't wait for a critical bug. Find a low-severity issue in a minor protocol. Write it up properly. Volume builds skill. Skill eventually finds critical.

---

## Feedback Loops

> ***136. Ask for pre-submission reviews*** - Find a trusted peer. Send them your draft report. Ask: "Is this clear? Is my severity justified? Did I miss anything?" Catch mistakes before judges do.

> ***137. Track your false positive rate*** - Of every ten suspicions, how many become real findings? High false positive rate means you're wasting time. Low false positive rate might mean you're missing edge cases. Calibrate.

> ***138. Time your review sessions*** - How long does it take you to understand a new protocol? How long to find your first lead? Tracking time reveals inefficiencies. What you measure improves.

> ***139. Keep a "blind spot" list*** - The last three bugs you missed. The last three invalid reports you submitted. What do they have in common? Patterns in your blindness are your highest-leverage improvement areas.

> ***140. Get a mentor or peer group*** - Someone slightly ahead of you who reviews your approach. A small group that meets weekly to discuss tricky findings. Isolation is slow. Community accelerates.

---

## Depth Over Breadth

> ***141. Know ten protocols deeply, not a hundred shallowly*** - Deep knowledge of a lending protocol reveals vulnerabilities that surface scanning never sees. Resist the urge to jump between codebases. Stay long enough to really understand.

> ***142. Read the entire codebase, not just the diff*** - Audits often scope "changed files only." That's a mistake. Changed code interacts with unchanged code in unexpected ways. Read everything.

> ***143. Understand the protocol's history*** - Previous audits. Previous bugs. Previous governance proposals. The past predicts the future. Teams repeat mistakes.

> ***144. Use the protocol as a user first*** - Deposit real testnet funds. Withdraw. Claim rewards. Upgrade. You can't audit something you've never used. User experience reveals implementation gaps.

> ***145. Build the protocol from source*** - Deploy it locally. Run the test suite. Modify parameters. Break things intentionally. Reading is passive. Building is active. Active learning sticks.

---

## Staying Current

> ***146. Follow EIP discussions, not just final EIPs*** - The debate around a proposal reveals edge cases and attack vectors. Read the GitHub threads. Understanding why a design was chosen (or rejected) teaches more than the final spec.

> ***147. Watch for new compiler versions*** - Each Solidity release fixes old bugs and potentially introduces new ones. Review the changelog. Test the new version on old code. Be early.

> ***148. Monitor new DeFi primitives*** - ERC-4626 (tokenized vaults), ERC-4337 (account abstraction), ERC-5219 (on-chain tokens with hooks). New standards mean new assumptions. New assumptions mean new bugs.

> ***149. Subscribe to security-focused newsletters*** - Rekt. DeFi Safety. Security Alliance. Weekly updates keep you aware of novel attack patterns without hunting for them yourself.

> ***150. Accept that you will never know everything*** - The field moves too fast. New vulnerabilities emerge. New patterns appear. New tools release. This is not a weakness — it's a feature. You will always have something new to learn. That's the gift.
