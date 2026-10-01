**POWERFARM CANON**

Powerfarm Operating System

How Powerfarm decides, allocates work, changes, and keeps the company coherent without excess process

| **DOCUMENT**  | PF-03             |
|---------------|-------------------|
| **STATUS**    | **CANONICAL**     |
| **VERSION**   | 1.6               |
| **EFFECTIVE** | 1 October 2026    |

| **OWNS**         | Decision ownership, work lifecycle, public operating boundaries, build-vs-use, resource allocation, exceptions, institutional drift, documentation governance, and durable operating rules. |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **DOES NOT OWN** | Research methodology (PF-02), detailed internal materialization architecture (PA-01), implementation-level technical system design and technology-specific standards (PF-04), or product/commercial doctrine (PF-05).                                                                   |

> **Normative language**
>
> MUST means required unless this canon is changed. SHOULD means the default and a material deviation needs a reason. MAY means optional.

# 1. Operating doctrine

Powerfarm is a small research institution operating in a fast-changing technical environment. Its operating system therefore optimizes for clarity, speed of learning, reversible change, and accumulated knowledge rather than procedural volume.

> **Minimum-process rule**
>
> A process, meeting, approval, template, or recurring artifact must earn its existence by reducing meaningful risk, coordination cost, repeated confusion, or loss of knowledge. If the cost of the process exceeds the expected cost of the failure it prevents, simplify or remove it.

Powerfarm's durable product is accumulated knowledge about how to produce and operate software. Specific tools, frameworks, runtimes, databases, models, and vendors are replaceable when better alternatives appear.

# 2. Operating principles

| **Principle**                               | **Operating meaning**                                                                                                              |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| One owner                                   | Every consequential piece of work has one clearly accountable owner, even when many people or agents contribute.                   |
| Decision at the lowest competent level      | Escalate when authority, irreversible consequence, material risk, or cross-system conflict requires it, not by habit.              |
| Reversibility matters                       | Reversible decisions move quickly. Irreversible or expensive-to-reverse decisions receive proportionally more evidence and review. |
| Write the decision, not the theater         | A short durable record is preferred to a meeting whose reasoning disappears.                                                       |
| Default to action with explicit uncertainty | Uncertainty can coexist with action when the downside is bounded and the state is recorded.                                        |
| Build thin                                  | Custom infrastructure exists only where it creates differentiated Powerfarm value.                                                 |
| Preserve history                            | Current recognized assertions can change; prior recognized assertions remain reconstructable.                                     |
| Exceptions are data                         | Repeated exceptions indicate either operational drift or a rule that should change.                                                |
| Cadence follows need                        | Recurring rituals are created only when the underlying need recurs.                                                                |
| Automation serves judgment                  | Agents and automation reduce coordination and execution burden, but must not conceal ownership or evidence.                        |

# 3. Public operating architecture boundary

Powerfarm's public operating model is organized around three durable sectors:

```text
Research      Continuity      Identity
learns        runs            remembers
```

Research learns how to produce software. Continuity materializes authorized transitions and preserves their evidence. Identity records what Powerfarm recognizes and which relationships grant authority. Interfaces, projections, execution substrates and storage substrates serve these sectors; they do not become additional institutional sectors merely because they are useful.

The detailed materialization of this model is private internal architecture. It is maintained in `PA-01 Powerfarm Internal Architecture` and must remain subordinate to this canon and to the normative specifications. The private document may choose providers, schemas, deployment shapes and local paths; it cannot change what Powerfarm means by a person, object, contract, version, grant, receipt or recognized state.

## 3.1 Durable boundaries

Powerfarm keeps the following boundaries explicit:

| Boundary | Public meaning |
|---|---|
| Authentication | A standards-based identity service can verify a credential and issue a token. |
| Institutional recognition | The Registry recognizes people, objects and contracts; grants and acts are contract kinds, not a fourth institutional category. |
| Immutable content | A content-addressed store preserves exact bytes by digest. |
| Semantics | Minivault describes promoted objects, relations, revisions and explanations. |
| Execution | Continuity materializes an authorized transition and records what happened. |
| Projection | Interfaces and search views organize recognized information for a reader; they are disposable. |
| Evidence | Important assertions carry provenance and a receipt that can be independently checked. |

Authentication is not institutional recognition. Possession of bytes is not authority. A projection is not a source of truth. A successful transport request is not proof of an effect when the effect still needs observation or verification.

## 3.2 State, contracts and rebuildability

Powerfarm follows three public rules:

- **State is local.** Operational state belongs to the application or service whose contract gives it authority over that state.
- **Contracts are global.** Institutional relationships, grants, ownership and authority are explicit and discoverable through recognized contracts.
- **Contracts have time and evidence.** Registration, recognition, validity, obligations, witnesses, uncertainty and consequences remain distinguishable; a projection may summarize them but cannot erase their history.
- **Everything institutional is rebuildable.** Recognized state can be reconstructed from preserved content, contracts and the ordered record of institutional acts. A provider, interface or storage engine can change without changing the institution when names, contracts and evidence remain intact.

The public representation order remains:

```text
intent → standard → Powerfarm contract → graph/declaration → schema/data → code → effects
```

The exact provider, database, folder layout, OAuth implementation and runtime belong to the private architecture or a versioned specification. They are replaceable materializations, not public canon.

## 3.3 Receipts as the common evidence envelope

Material operations follow this conceptual chain:

```text
INTENT → AUTHENTICATE → AUTHORIZE → EXECUTE → OBSERVE → RECEIPT → RECOGNIZE
```

A read may stop after observation and a receipt. A state-changing operation cannot become institutionally current without the recognition step required by its contract.

A receipt identifies the principal, contract, operation, target, input and output evidence, executor, time, result and supporting digest. The receipt says what happened and what evidence supports it; it does not manufacture authority or truth.

## 3.4 Public architecture freeze rule

Powerfarm SHOULD NOT introduce a new durable subsystem until an existing sector, service, contract, projection or substrate has been shown insufficient. The default next move is to implement and test the current model, preserve the evidence and revise the relevant specification when the boundary is genuinely wrong.

The internal architecture may evolve quickly. It must publish the consequence of a material change through a versioned decision record and keep the public canon stable unless the institution's durable commitments have changed.

# 4. Work lifecycle

1. Sense: notice a change, problem, opportunity, request, failure, or unresolved decision.

2. Frame: define the outcome, owner, constraints, and what evidence is already known.

3. Decide: choose the next action at the appropriate level of rigor.

4. Execute: perform the work with the smallest sufficient process and tools.

5. Verify: check that the intended outcome occurred and that material risks are bounded.

6. Learn: capture what changed our understanding, including failures and surprises.

7. Update: revise the relevant current state, recommendation, product, system, or canon when justified.

Not every task needs a formal artifact for every stage. The lifecycle describes the logic that must remain available, not a mandatory seven-form workflow.

# 5. Decision ownership and records

A consequential decision SHOULD have one Decision Owner. Contributors may research, challenge, execute, or verify, but accountability remains explicit.

A durable Decision Record is required when a choice is expensive to reverse, changes a canonical rule, creates material proprietary infrastructure, materially affects customers or public claims, creates a security/privacy boundary, or is likely to be revisited later without obvious context.

| **Minimum field**  | **Question**                                          |
|--------------------|-------------------------------------------------------|
| Decision           | What are we choosing?                                 |
| Owner              | Who is accountable for the decision?                  |
| Context            | What problem or opportunity caused the decision?      |
| Options            | What credible alternatives were considered?           |
| Evidence           | What supports the choice, and what remains uncertain? |
| Consequences       | What do we gain, give up, or risk?                    |
| Reversal / trigger | What event should cause reconsideration?              |
| Date / version     | When did this become current?                         |

# 6. Decision classes

Powerfarm does not require a different bureaucracy for every kind of decision, but the evidence that matters differs by class.

| **Class**     | **Primary question**                                                                                                  |
|---------------|-----------------------------------------------------------------------------------------------------------------------|
| Research      | What decision could new evidence change, and how much rigor is justified?                                             |
| Technical     | Does this improve outcomes, evidence, reliability, safety, economics, or replaceability enough to justify complexity? |
| Product       | Does this convert Powerfarm knowledge into repeated external value without distorting research integrity?             |
| Resource      | What is the highest-value use of money, compute, hardware, and human attention under current constraints?             |
| Institutional | Does this alter a durable rule about what Powerfarm is or how it must operate?                                        |

# 7. Build versus use

> **Default**
>
> Use sufficiently capable external technology before building an equivalent proprietary component.

Before a material internal build, the owner SHOULD answer:

- Which Powerfarm outcome or canonical promise requires this capability?

- Which credible external alternatives were evaluated?

- What differentiated value would custom work create in evidence, knowledge, safety, reliability, economics, or decision capability?

- What maintenance and lock-in will Powerfarm inherit?

- How replaceable will the component remain?

- What measurable event would cause us to stop, replace, or simplify it?

If an external capability is sufficiently good and a proprietary implementation does not create material Powerfarm-specific value, Powerfarm SHOULD NOT build it.

# 8. Resource allocation

Powerfarm allocates scarce resources to maximize decision value and compounding knowledge, not activity. Resource decisions SHOULD consider:

- Decision consequence and expected value of better information.

- Strategic compounding: whether the work creates reusable evidence, methods, or product capability.

- Time sensitivity and frontier freshness.

- Reversibility and downside if wrong.

- Monetary cost, compute, hardware occupancy, and human attention.

- External leverage: whether buying, renting, or integrating is superior to building.

- Opportunity cost: what important work is displaced.

Budget is a constraint on the decision, not a prestige signal. Powerfarm may exchange time for money, money for higher quality, or redundancy for confidence when the decision warrants it.

# 9. Exceptions

Rules exist to improve decisions, not to punish reality. A material exception MAY be accepted when it is explicit and bounded.

| **Exception field** | **Requirement**                                        |
|---------------------|--------------------------------------------------------|
| Rule                | Which rule or default is being departed from?          |
| Reason              | Why is the exception better under current constraints? |
| Evidence            | What supports the exception?                           |
| Owner               | Who owns the consequence?                              |
| Expiry / trigger    | When must it be reconsidered?                          |
| Remediation         | What must change if the exception is temporary?        |

Recurring exceptions to the same rule are evidence. They SHOULD trigger either correction of behavior or revision of the rule.

# 10. Conformance without bureaucracy

Formal conformance review is reserved for decisions where contradiction would be materially costly: canonical changes, strong public claims, important customer commitments, significant proprietary builds, or security/privacy boundaries.

A review asks:

1. Does the decision conflict with the Charter or another canonical rule?

2. Is the relevant evidence strong enough for the consequence?

3. Were credible external alternatives considered?

4. Are uncertainty, trade-offs, and exceptions explicit?

5. Does the decision preserve replaceability and historical traceability where material?

6. Does the subject create real outcome, knowledge, safety, or economic value proportional to its complexity?

7. What future event should trigger reassessment?

The output is simple: CONFORMING, JUSTIFIED EXCEPTION, CHANGE REQUIRED, or CANON REVIEW. Powerfarm does not maintain conformance scoring for its own sake.

# 11. Institutional and frontier drift

Institutional drift is the gap between Powerfarm's actual behavior and its durable commitments. Frontier drift is the gap between current practice and the sufficiently mature technology frontier.

- Growing proprietary maintenance without corresponding knowledge or product value.

- Repeated reliance on stale evidence or recommendations.

- Vendor dependence that weakens independent judgment or replaceability.

- Benchmarks defended as products rather than replaced as instruments.

- Increasing human rescue while autonomy claims remain unchanged.

- Recurring exceptions that have become the real operating rule.

- A major external advance that makes the current technical approach materially inferior.

- Architectural growth that introduces new durable subsystems without evidence that existing boundaries are insufficient.

A drift review ends in one of four outcomes: correct behavior, accept a temporary deviation, change method/implementation, or revise canon.

# 12. Incidents and learning

A material technical, operational, customer, security, or epistemic failure SHOULD produce a learning record when the lesson is likely to recur. The purpose is not blame; it is to prevent repeated ignorance.

The record SHOULD capture event, impact, causal factors, detection, recovery, what signals were missed, actions, owner, and follow-up trigger. High-confidence research claims found seriously misleading are treated as epistemic incidents under PF-02.

# 13. Documentation system

Powerfarm deliberately separates authority from volume. Documents are classified by role:

| **Class**         | **Meaning**                                                                                                                                    |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Canonical         | One of PF-01 through PF-05. Defines current public institutional commitments and recognized operating rules.                               |
| Standard instance | A recurring document type from the archived catalog instantiated because a real need exists. It can be authoritative within its scope without becoming canon. |
| Working           | Proposal, draft, investigation, notes, or active design. May change freely.                                                                    |
| Reference         | Useful explanation, evidence, report, external source, or technical detail that does not define company-wide authority.                       |
| Historical        | Superseded material retained to reconstruct decisions, methods, and past recognized state.                                                     |

- One important concept has one canonical home.

- A new document is not created merely to avoid editing an existing one.

- The former PF-06 catalog is retained as historical reference. Its entries create no obligation to write a document.

- The default response to a new documentation need is: can the existing canon or an existing standard instance absorb this cleanly?

- A document without an owner, reader, decision, or maintenance reason SHOULD be archived or deleted rather than kept "just in case."

- The public operating boundary is maintained here. Detailed internal materialization is maintained in the private PA-01 architecture document. PA-01 is not a sixth public canon document.

# 14. Change and history

Powerfarm expects methods, products, systems, recommendations, recognized assertions, and implementations to change. Material current-state changes are versioned. Supersession preserves the prior version, the reason for change, and the date the new state became current.

> **Anti-dogma rule**
>
> A research institution that never changes is failing. A research institution that changes without knowing why is also failing.

# 15. Meetings and recurring cadence

No meeting, report, review, or recurring ritual is canonical by default. A cadence is introduced only when a recurring coordination or risk problem exists, and it is removed when that need disappears. Asynchronous written state is preferred when it provides equivalent clarity with lower cost.

# 16. Operating rules

1. Keep authority small and explicit.

2. Let reversible decisions move quickly.

3. Write consequential decisions so future Powerfarm can understand present Powerfarm.

4. Use external capability before reproducing it internally.

5. Treat exceptions and incidents as evidence.

6. Let process scale with consequence, not with organizational anxiety.

7. Change implementation aggressively when reality improves.

8. Change canon deliberately when identity or durable operating truth changes.

9. Keep operational state with the software that owns it unless a stronger boundary is justified.

10. Use contracts to make institutional relationships explicit.

11. Separate evidence, semantic triggering, execution claims, materialized effects, and verification.

12. Do not create a new durable subsystem merely because a new responsibility appears; first attempt to express it through the current model.

13. Preserve exact immutable content when history or composition requires it, but do not confuse byte identity with authority.

14. Prefer provenance-bearing assertions over opaque status.

15. Treat active model context as a temporary working set; prefer durable references and on-demand loading for large reusable immutable content where practical.

16. Bring institutional things into existence through recorded acts, never through bulk seeding, so that the institution can always be rebuilt by replaying them.

---

# Appendix A. Formal Executability Model v0.1

This appendix is normative for the conceptual separation of responsibilities. Concrete implementation mechanisms belong in PF-04 or subordinate technical specifications so long as they preserve these semantics.

## A.1 Evidence domains

For executable contract `c`, let:

- `T_c( t_hat )` be the temporal predicate evaluated over temporal evidence available to Heartime;
- `O_c( w_hat )` be the observational predicate evaluated over observational evidence available to Antenna.

Powerfarm does not require access to an objective complete world-state or perfect universal time.

The admissible region is therefore:

```text
R_c = { (t_hat, w_hat) | T_c(t_hat) AND O_c(w_hat) }
```

The architecture MUST NOT silently replace `t_hat` or `w_hat` with an assumed omniscient `t` or `w` in its execution semantics.

## A.2 Readiness

```text
Ready_c = T_c(t_hat) AND O_c(w_hat)
```

Events, observations, clock evidence, retries, and other inputs update evidence. Evidence updates predicates. Predicate convergence creates readiness.

The fundamental transition is therefore entry into an admissible region, not necessarily receipt of a conventional event:

```text
outside admissible region
        ↓
inside admissible region
```

or, equivalently:

```text
0 → 1
```

in satisfaction of the executable condition.

## A.3 Policy and trigger

Readiness alone does not determine whether execution should occur.

Let `H_c` denote the relevant causal history and `pi_c` the contract policy.

Policy evaluates the meaning of readiness:

```text
Trigger_c = pi_c(Ready_c, H_c)
```

Policy MAY define semantics including:

- edge-triggered or level-triggered behavior;
- first match only or retriggering;
- hold-for duration;
- ordering between temporal and observational evidence;
- buffering or discard;
- expiration;
- retry eligibility;
- concurrency policy;
- cancellation;
- compensation eligibility.

Policy determines whether readiness should produce a trigger. It does not itself grant exclusive execution ownership.

## A.4 Claim and generation

Execution coordination is distinct from contract semantics.

For a trigger associated with contract generation `generation_c`:

```text
Claim_c = AtomicAcquire(Trigger_c, generation_c)
```

Multiple workers MAY observe the same readiness or trigger. Where the contract requires exclusive materialization, only one valid claim may authorize execution for the relevant generation.

The atomic acquisition mechanism MAY vary by implementation, but the separation between policy and coordination MUST remain explicit.

## A.5 Materialization

A valid claim authorizes Continuity to materialize the contract effect:

```text
State' = Continuity.materialize(E_c, Claim_c)
```

`E_c` is the effect or authorized state transition.

Continuity preserves causal execution state and SHOULD represent uncertainty when effect certainty cannot yet be established.

## A.6 Verification

Let `w_hat_prime` denote observational evidence available after materialization.

Verification is:

```text
Verified_c = V_c(w_hat_prime)
```

Verification determines what Powerfarm may subsequently assert about the effect.

A transport acknowledgement MAY contribute evidence but MUST NOT automatically be treated as proof that the intended world effect occurred when those meanings differ.

## A.7 Contract semantic core

The semantic core of an executable contract is:

```text
C = (T, O, pi, E, V)
```

where:

- `T` = temporal condition;
- `O` = observational condition;
- `pi` = semantic trigger policy;
- `E` = effect or authorized transition;
- `V` = verification predicate.

Execution coordination adds contract generation and claim semantics around this core rather than being conflated with policy.

## A.8 Responsibility map

| **Operation** | **Primary responsibility** |
|---|---|
| `T_c(t_hat)` | Heartime temporal evidence and predicate evaluation |
| `O_c(w_hat)` | Antenna observational evidence and predicate evaluation |
| `Ready_c` | Contract predicate convergence |
| `Trigger_c` | Contract policy `pi_c` |
| `Claim_c` | Atomic execution coordination |
| `materialize(E_c, Claim_c)` | Continuity |
| `V_c(w_hat_prime)` | Verification over subsequent evidence |

This separation is architectural. Implementations MAY co-locate mechanisms, but MUST preserve the semantic boundaries.

## A.9 Conceptual contract lifecycle

```text
dormant
   ↓
armed
   ├── waiting_temporal
   ├── waiting_observation
   └── waiting_both
             ↓
           ready
             ↓
          trigger
             ↓
        atomic claim
             ↓
          claimed
             ↓
         executing
       /     |       \
    done   failed   uncertain
             ↓
       retry / compensate
```

Cancellation, expiration, supersession, and retirement MAY also terminate or redirect the lifecycle according to contract policy.

## A.10 Degenerate cases

The model supports common patterns without defining separate foundational primitives.

### Webhook

```text
T = always admissible
O = arrival observed
```

### Cron-like execution

```text
T = scheduled temporal condition
O = true
```

### Retry

```text
T = retry_at reached
O = prior effect remains unverified
```

### Deadline

```text
T = deadline condition
O = completion state
```

### Physical class example

```text
T = 07:00 ≤ time evidence ≤ 08:00
O = teacher_present AND students_present AND room_ready
```

The class becomes ready only when temporal and observational predicates converge under available evidence. Policy then determines whether that readiness produces a trigger.

---

# Appendix B. Architectural mantra

```text
Research creates and learns.
GitHub explains.
Content Store preserves and carries immutable values.
Registry recognizes through the applicable contract, including an act contract.
Identity resolves provider credentials to a principal; Registry contracts authorize.
Antenna maintains observational evidence.
Heartime maintains temporal evidence.
Policy determines semantic triggering.
Atomic claim establishes execution ownership.
Continuity materializes transitions.
Applications remember themselves.
Recorded acts rebuild.
Search finds.
```

> **State is local. Contracts are global. Bytes are immutable when preserved. Authority is explicit. Execution is causal. Everything institutional is rebuildable. Knowledge is the durable product.**
