# QT Cyborg Charter
## NJC-ARCH-001 | Institutional Governance Instrument

**Charter ID:** QT-CYBORG-CHARTER-001  
**Version:** 1.0  
**Status:** Proposed internal governance standard  
**Governing maxim:** *VERITAS ANTE ASSERTIONEM* — Truth Before Assertion

### Preamble

This Charter establishes the governance principles for the design, operation, validation, review, and controlled release of the NJC-ARCH-001 validation pipeline and any systems expressly brought within its scope. It is a faith-informed, nonbinding internal policy instrument. It does not create a government body, court, public office, legal jurisdiction, regulatory mandate, or authority over persons or institutions outside its adopting organization.

Technology is an instrument entrusted to accountable people. Neither automation nor artificial intelligence may convert an assertion into a fact, a recommendation into an order, or technical access into institutional authority.

### Article I — Purpose and scope

1. Establish traceable, evidence-based validation and release controls.
2. Preserve the separation of automated workload functions from human review and release authorization.
3. Maintain reproducible records of decisions, changes, exceptions, and validation results.
4. Apply only to repositories, environments, data, and workflows explicitly designated by an authorized adopting organization.
5. Require documented authorization before processing personal, confidential, regulated, or third-party data.

### Article II — Governing principles

- **Truth before assertion:** Claims must be supported by inspectable evidence, provenance, and reproducible methods.
- **Human accountability:** A named, authorized human remains accountable for consequential institutional decisions.
- **Least privilege:** Every identity receives only the permissions required for its assigned function.
- **Separation of duties:** A validator may not authorize release of the same item it validated.
- **Due process and contestability:** Material decisions must have a recorded rationale and a practical route for review or correction.
- **Privacy and proportionality:** Collect and retain only data necessary for a stated, authorized purpose.
- **Security by design:** Protect credentials, keys, evidence, logs, and production environments against unauthorized access or alteration.
- **Accessibility and non-discrimination:** Validation criteria must be documented, relevant to the task, and reviewed for avoidable exclusion or disparate impact.
- **Reversibility:** Releases and material changes must have rollback, suspension, or remediation procedures where technically feasible.

### Article III — Roles and authority

1. **System owner:** Defines scope, appoints authorized stewards, approves risk tolerances, and accepts operational accountability.
2. **Workload validator:** Executes automated tests using a non-human workload identity. Its authority is limited to validation actions.
3. **Human reviewer:** Examines evidence, exceptions, limitations, and test results; records an independent disposition.
4. **Release authority:** A separately authorized human decides whether a validated item may be released.
5. **Independent auditor:** May inspect evidence and control operation without modifying the records under review.
6. **AI systems and agents:** May assist with analysis, classification, drafting, and recommendations within granted permissions. They may not appoint themselves as authorities, grant permissions, approve their own work, suppress adverse evidence, or make final release decisions.

No title or role in this Charter grants civil, judicial, regulatory, or governmental authority.

### Article IV — Validation and release protocol

The default release sequence is:

**Automated validation → Human review → Independent release authorization → Controlled promotion.**

1. Each release candidate must identify its baseline, version, inputs, test suite, environment, and evidence location.
2. A failed mandatory positive or negative gate blocks promotion.
3. A skipped, unavailable, or inconclusive test must be recorded as such; it must never be represented as a pass.
4. Human reviewers must examine material failures, exceptions, provenance, and known limitations.
5. The validator and release authority must have distinct authenticated identities. A same-subject validation/release pairing is rejected.
6. Any override requires documented authority, rationale, scope, duration, compensating controls, and an audit record. No override may falsify a test result or erase a failure.
7. Release authorization is not proof of legal compliance, factual perfection, safety in every context, or endorsement by an external institution.

### Article V — Evidence and audit integrity

1. Preserve append-only audit records where supported by the storage architecture.
2. Each ledger entry must bind the canonicalized event payload to its predecessor hash and record the applicable algorithm and schema version.
3. Verification must fail closed on malformed entries, missing predecessors, hash mismatches, unauthorized identity transitions, or broken sequence continuity.
4. Hash chaining provides tamper evidence, not proof that the original event was truthful, complete, or authorized.
5. Record timestamps, actor identity, action, target, decision, rationale, software version, and relevant evidence references, while minimizing sensitive data.
6. Retention, access, export, and deletion must follow an approved records schedule and applicable law.

### Article VI — Security, privacy, and data stewardship

- Store secrets in an approved secret manager; never commit tokens, private keys, passwords, or production credentials.
- Validate OIDC issuer, audience, signature, key rotation, expiry, and required claims.
- Separate development, test, staging, and production credentials and data.
- Use least-privilege database roles; routine writers must not receive UPDATE, DELETE, or TRUNCATE rights on protected audit records.
- Encrypt sensitive data in transit and at rest where appropriate; restrict access and log privileged operations.
- Do not migrate, disclose, or combine data across databases without documented ownership or lawful authority, purpose limitation, compatible permissions, data mapping, quality checks, and an approved rollback plan.
- Provide incident reporting, containment, preservation, notification, and recovery procedures.

### Article VII — Fair review, correction, and appeals

Any affected stakeholder with a legitimate interest under the adopting organization's policies may request correction of inaccurate records, reconsideration of a disposition, or review of a process failure. Requests must be routed to a reviewer who did not make the challenged decision where practicable. Decisions, supporting evidence, conflicts of interest, and remediation must be recorded. This internal process does not replace statutory rights, contractual remedies, regulatory processes, or access to courts.

### Article VIII — Change control and accountability

1. Changes to baselines, tests, prompts, models, policies, permissions, schemas, or release criteria require version control, a change rationale, impact assessment, and review.
2. Material changes require revalidation before production use.
3. The system owner must periodically review access, control effectiveness, unresolved risks, retention, and incident history.
4. Known limitations, false-positive/false-negative risks, model uncertainty, and unsupported claims must be disclosed to decision-makers.
5. If evidence integrity or separation of duties cannot be established, suspend the affected release path until the deficiency is resolved or formally risk-accepted by an authorized human under documented policy.

### Article IX — Adoption, interpretation, and amendment

This Charter takes effect only when adopted in writing by the authorized owner of the relevant system or organization. The adopting organization must identify the owner, covered systems, effective date, review interval, and applicable supplemental policies. Amendments require version history, rationale, impact review, and approval by the adopting authority. In case of conflict with applicable law, binding contracts, or superior organizational policy, those controlling requirements prevail.

---

**Foundational rule:** No system may certify its own authority. No agent may approve its own consequential work. No release may outrun its evidence.

*VERITAS ANTE ASSERTIONEM — Truth Before Assertion.*
