# The Claim-Strength Profile: Publisher-Authored Interpretation Limits for Machine Readers

**Status: PUBLISHED CANDIDATE surface — not a confirmed component of any
system. Maturity: operator-derived, operationally exercised
(bespoke form), externally unvalidated. The profile schema below is a
SPECIFICATION SKELETON; no validator ships with this document.**

Provenance of this text: it passed a multi-round external adversarial
review gate (round 1: two independent reviewers in parallel; rounds 2-3:
two further reviewer lineages; final round verdicts drove the last
revisions) across 2026-08-21/22. Its claims of absence are bounded to
documented search scopes.
## The problem this names

Every deployed machine-readable publisher signal governs ACCESS and USE:
robots.txt and its AI successors govern crawling; IETF AIPREF preferences
govern collection and processing; ODRL's AI vocabulary actions are all
input-side; licenses and provenance credentials govern reuse and
authenticity. None of them lets a publisher say what a machine reader may
CONCLUDE from permitted text — at what strength, in what wording. The
standards bodies have declined this scope on record: AIPREF's charter is
collection-and-processing; the most ambitious individual drafts state
they do not propose expanding it (draft-hood-aipref-earmark-00, which
says so explicitly; also draft-wallace-aipref-grant-binding,
draft-zehta-aipref-parameters — all ingestion-side).

Meanwhile the mechanism exists — fragmented. Verified public artifacts,
each invented privately, none interoperable: publisher-authored claim-type
labels with permitted surface wording; an explicit
do-not-upgrade-conditional-to-established-fact prohibition; a machine
policy-surface hierarchy with an ordered rule of interpretation and a
non-goals section; typed public misreading registries with declared
empty-state semantics; a robots-style file with a `derivative:` directive.
(All acknowledged by name in the prior-art section; a related but
distinct pattern — claim-level provenance with graded transmitter
reliability and quarantine routing — is also published, arXiv 2607.24117,
and is cited, not claimed.) Eight one-off artifacts (the eighth verified and added after external
review), no shared vocabulary, no schema, no conformance validator: a STANDARDS-PRODUCT gap, not a mechanism-absence
gap. This document is the integration profile.

## What this document claims

Not the mechanism (it exists, fragmented — above). Not enforcement (an
interpretation limit is preference-signaling; reader-side honoring is the
only lever, exactly as with every access preference). The claim is the
INTEROPERABLE FORM: the CONJUNCTION corpus-agnostic + machine-targeted +
publisher-authored, in one profile — evidence-conditioned strength
ceilings exist in domain-bound form (GRADE Summary-of-Findings; FDA SPL,
both conceded below), and the eight fragments each hold one private
piece; no public artifact holds the conjunction, nor ships a public
conformance validator. Search scope: English-language web, arXiv, standards trackers,
surveyed 2026-08-21, medium depth, recorded queries.

## The profile (specification skeleton)

A conforming profile document declares, per corpus or per document:

1. **Evidence classes** the publisher distinguishes (e.g. stated-in-text /
   publisher-confirmed / structurally-inferred / absent), each with a
   machine-checkable definition of what a reader must HOLD to claim it.
2. **Strength ceiling per evidence class**: the maximum claim strength a
   reader may assert from that evidence class alone, on an enumerated
   ladder (e.g. describes / states / supports / establishes), with
   PERMITTED WORDING per level — example phrasings that conform, and the
   upgrade move that violates ("the file describes X" may never become
   "X is established" without crossing an evidence-class boundary).
3. **Negative frame list**: enumerated characterizations the publisher
   declares misrepresentative ("do not summarize as…"), machine-readable.
4. **Correction linkage**: a pointer to the publisher's typed misreading
   register, with declared empty-state semantics (an empty register means
   only that no confirmed cases are recorded — never that no misreading
   exists).
5. **Fail-closed interpretation defaults**: unknown remains unknown;
   absence of evidence does not expand inference permission; unresolved
   conflict does not resolve by recency; partial retrieval does not
   become complete access.
6. **Temporal non-authority**: the date types the corpus carries
   (creation, publication, registration, semantic-status, supersession),
   with chronological precedence explicitly denied semantic precedence —
   a newer file supersedes only by explicit statement.
7. **Self-scope**: the profile binds interpretation CLAIMS ABOUT the
   corpus, not private reasoning; it constrains what a conforming reader
   ASSERTS, which is the only surface a publisher can address.

A CONFORMANCE VALIDATOR (unbuilt; its requirements are part of this
specification) checks a reader's output text against the profile:
strength-ladder wording per claimed evidence class, negative-frame
violations, and correction-register acknowledgment. Validation output
confers no authority; it is evidence.

**The validator's honest ceiling (resolved in-text after external
review).** A ladder bound to natural-language permitted wording makes
conformance checking LEXICAL: paraphrase, translation, and semantically
upgraded claims wearing conforming surface words all evade it. Version 1
of this profile therefore claims lexical conformance ONLY, and says so:
the validator detects wording-level violations and nothing deeper. The
stated upgrade path is binding the ladder to TYPED CLAIM RELATIONS
(assertion-type tags a conforming reader emits alongside its prose)
rather than surface phrasing — at which point conformance becomes
type-checking and the wording lexicon becomes documentation. Readers of
v1 should treat lexical conformance as a tripwire, not a proof.

**Attribution, not world-truth (the boundary that keeps this from being
a censorship interface).** The profile constrains what may be claimed AS
GROUNDED IN THIS CORPUS — "based solely on this corpus, X is described"
— and nothing else. It has NO authority over conclusions grounded in
external evidence: a conforming reader remains entirely free to
establish X from independent sources, and profile conformance may never
be cited as if it bounded what is true in the world. A publisher profile
invoked to suppress externally-grounded claims is MISUSED, and a
conformance validator must treat external-evidence claims as out of its
jurisdiction by construction. Where corpus-attributed and
externally-grounded statements appear together, only the attribution
clause is checkable: "this corpus describes X; independent evidence
establishes X" is fully conforming. Under the v1 lexical validator,
jurisdiction is determined fail-closed: external-evidence grounding must
be EXPLICITLY MARKED in the reader's output; an unmarked or mixed claim
is treated as corpus-attributed and checked against the profile. The
marking convention is part of the profile's conformance surface, which
keeps jurisdiction decidable at the lexical ceiling v1 honestly claims.

**Scope of binding.** The profile binds everything a reader ASSERTS TO A
DOWNSTREAM CONSUMER — summaries, conclusions, syntheses, any derived
claim presented outward. Private reasoning is unbindable and out of
scope; relabeling an outward assertion "synthesis" changes nothing.

**Layered precedence.** Where document-level and corpus-level profiles
both apply: a document-level profile may only TIGHTEN the corpus-level
profile, never loosen it; on any conflict the MORE RESTRICTIVE ceiling
wins, without exception (the conflict-attribute pattern, borrowed from
ODRL's conflict strategies). The earlier two-clause form collided with
itself and is replaced by this single rule.
Against access-side instruments there is no true conflict: AIPREF/ODRL
gate input, this profile gates output assertions; access denied makes the
profile moot, access granted leaves both in force.

**Minimal tier.** A single field — `max-claim-strength: <level>` per
document — is a conforming degenerate profile, acknowledged as the floor;
the full apparatus earns its keep only where evidence classes genuinely
carry different ceilings.

## Rule register

| Element | State | Enforcement today |
|---|---|---|
| 1–2 evidence classes & ceilings | EXPERIMENTAL | none (spec only) |
| 3 negative frame list | HARD once a checker exists (list matching is mechanical) | none (spec only) |
| 4 correction linkage & empty-state | HARD once a checker exists | none (spec only) |
| 5 fail-closed defaults | HARD (definitional) | none (spec only) |
| 6 temporal non-authority | HARD | none (spec only) |
| 7 self-scope | OWNER (scope changes reserved) | — |

## What this is NOT

Not enforceable on any reader (stated plainly; the leverage model is the
same reader-side honoring that AIPREF itself concedes). Not a licensing
instrument, an access preference, or a provenance credential — it
composes with all three. Not a claim that any fragment is ours: the eight
artifacts are prior art, named. Not a running system: no validator ships.

## Relation to prior art (acknowledged, by name)

Fragmented instances of the mechanism — all third-party (NONE is the
author's own project; stated because a reviewer rightly asked), each
resolved and content-verified 2026-08-21 in a recorded verification round
(the check confirmed each page exists and supports the one-line gloss);
locators (https scheme implied):
docs.wheelofheaven.world/ai-ingestion/system-prompts/ (claim-type labels
direct/framework/inferred/speculative with bracket-prefix wording rules);
dfife.github.io/for-ai.html — the IO Framework ("do not upgrade
conditional… to established fact"); gautierdorval.com/en/doctrine/
machine-policy-surfaces/ (surface hierarchy, non-goals, ordered
interpretation rule); geoscanai.co/registry (typed hallucination registry
with verbatim declared empty state); huggingface.co/datasets/2a-agency/
brand-semantic-integrity-registry (12 misreading patterns);
failureindex.ai (eight mechanism-typed failure modes); robots2.org
(`derivative:` directive; its summarization control is `quote:
short-only`); and — verified 2026-08-22 — pagup.com/en/ai-use-policy, a
vendor-published machine-facing surface with named layers, a nine-tier
precedence hierarchy, per-claim-family admissible authorities (some
families inadmissible), and explicit downgrade/abstention rules — the
closest in-the-wild neighbor to this profile, self-scoped to claims
about its own company, unilateral, and without any adopting consumer:
an eighth fragment, not a convention. Corpus-agnostic reading guidance without ceilings:
llms.txt (llmstxt.org, 2024) — publisher-authored, machine-directed, and
the closest thing to a deployed convention in this space; acknowledged as
a material neighbor. Domain-bound instances of ceilings-with-wording,
conceded as the mechanism in bounded form: GRADE Summary-of-Findings
tables (wording prescribed per certainty level — the ladder+wording
shape, for human readers of clinical evidence) and FDA Structured
Product Labeling (machine-readable, evidence-conditioned claim strength,
pharmaceutical domain). The delta this profile claims over both:
corpus-agnostic + machine-targeted + publisher-authored, together.
Reviewer-authored claim ratings: Schema.org ClaimReview (distinguished:
third-party review of claims, not publisher-side interpretation limits).
Adjacent claim-provenance schemas that stop at labelling status: Pramana
(arXiv 2605.20312); live claim registries with self-assessed conformance.
Claim-level graded provenance with quarantine routing: the Isnad-Rijal
framework (arXiv 2607.24117) — transmitter reliability, a different
axis. Ancestors for human readers: GRADE certainty language; journal
epistemic-status labels; IPCC confidence vocabulary. Standards that
declined the scope: IETF AIPREF (charter: collection and processing;
2026-04 interim minutes narrowing definitions); the ODRL AI vocabulary
draft at w3c.github.io/odrl/ai-vocab/ (W3C community-group DRAFT, not a
Recommendation — cited as such; its actions are input-side). The
inverted commercial direction: GEO/AI-visibility products building
"represent me more" on the same plumbing.

## Enforcement maturity (self-disclosure)

Nothing is enforced anywhere: no validator exists, no reader honors the
profile, and the publisher-side artifacts it integrates are one-off
conventions. The profile's entire near-term value is (a) giving the eight
existing artifacts a common target, (b) making "this reader conforms" a
checkable statement once the validator exists, and (c) the priority
record itself. If reader-side honoring never emerges, this remains
documentation of a vacant scope — that risk is accepted and stated.

## Possible relations (not asserted)

This surface emerged from one operating practice in parallel with other
candidate surfaces: lineage-aware-agent-governance,
lineage-admission-control, disclosure-order-review,
falsifiability-first-protocol, scoped-rejection. Common origin is asserted as a fact of production history; no relation
BEYOND common origin is asserted, and none is confirmed. Composition, dependency, or a unified framework
among any of them is possible and deliberately NOT asserted; no confirmed
relation exists, and none should be inferred from co-ownership, shared
vocabulary, or structural resemblance. Read under a
weakest-compatible-relation default: navigation adjacency. If a
composition is ever established it will be stated explicitly; absence of
that statement means it has not been.

## Public / internal boundary

The profile is corpus-agnostic by construction; nothing here describes
any particular corpus, its size, its structure, or its governance.
Non-inference runs both ways.

## Fork / derivative boundary

Source provenance is not inherited authority; attribution is not
endorsement; derivative decisions are not attributable upstream.

## Review questions (refutation invited)

1. Name a public, corpus-agnostic schema mapping evidence classes to
   strength ceilings WITH permitted wording. That defeats the integration
   claim within any scope.
2. Is the strength ladder expressible without natural-language wording
   examples — and if not, can conformance checking ever be more than
   phrase matching? (This may be the specification's weakest joint.)
3. Should the profile bind SUMMARIES only, or all derived claims? Where
   is the line between a reader's assertion and a reader's reasoning?
4. Does composing with AIPREF/ODRL create conflicts (an access-denied
   document with a permissive profile, or the reverse)? Define precedence
   or show it is unnecessary.
5. A simpler structure producing equivalent assurance is a successful
   challenge.

Negative findings are relevant findings.
