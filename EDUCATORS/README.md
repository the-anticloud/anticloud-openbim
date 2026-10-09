# Educators — OPENBIM

**Project:** OPENBIM  
**Category:** ARCHITECTURAL_DESIGN  
**Upstream:** see BENCH.json  
**Pinned commit:** `see BENCH.json`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `c561f36dc3f0677598bb19306e77866a0b5d46a25f993b3ac947241674bdbe32`  
**Date:** October 2026

## Teaching with OPENBIM

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `c561f36dc3f0677598bb19306e77866a0b5d46a25f993b3ac947241674bdbe32` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
