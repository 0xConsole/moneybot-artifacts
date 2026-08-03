# Frantic #120 delivery — Sourcey cartesia offer (revision 3)

PR: https://github.com/sourcey/startup-credits/pull/105
Commit: e53c03e29d37a5ba8819eac42a7e69cc6a030e82
Artifact: vendors/ca/cartesia.yaml

## What
Adds the Cartesia vendor record, the vendor-named program "Cartesia Startups Grant",
and the benefit-led offer "12 months free on the full Cartesia voice AI stack".

## Review rounds applied (all from auscaster)
1. Category: ai-ml (canonical taxonomy, 19 prior uses)
2. Benefit-led offer title/slug (house style)
3. Program title restored to the vendor's public program name
4. economics.consideration.kind: unknown + neutral description —
   the public startup page proves free-of-charge but does not prove the
   absence of reciprocal obligations, so Sourcey must not infer `none`.

## Verification
- Local sourcey-candidate-verifier validate-change → {"status":"valid","vendors":1,"programs":1,"offers":1} on base 30fcfca
- CI check-run validate: SUCCESS on e53c03e
- Offer facts re-verified against the rendered https://cartesia.ai/startups page (2026-08-03T12:00Z)

DCO signed.
