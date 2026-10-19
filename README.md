# Open-Source Bug Triage & Verification

This repository contains a log of my technical triage work. I actively monitor open-source platforms (like Supabase) to reproduce reported bugs, verify frontend/database issues, and validate community fixes.

## Reproductions

### Bug 1: SQL Editor Auto-Limit Syntax Error (Issue #51836)
**Status:** Reproduced & Confirmed
**Environment:** Chrome, Windows 11, EU-West region
**The Issue:** When auto-limit is enabled (e.g., 100 rows), writing `LIMIT ALL` or `LIMIT NULL` causes the SQL Editor to append a second `LIMIT 100`, generating invalid SQL (`select 1 limit all limit 100`).
**My Action:** Ran the exact reproduction steps on my end. Confirmed the syntax error and provided environment details to the developer for the fix.

### Bug 2: Table Editor Decimal Precision Rounding (Issue #51827)
**Status:** Reproduced & Confirmed
**Environment:** Chrome, Windows 11, EU-West region
**The Issue:** When filtering a high-precision decimal in the Table Editor, the UI rounds the number (due to JavaScript limits), resulting in "0 records" found.
**My Action:** Created a table with the exact decimal `0.123456789012345678901`. Applied the filter in the UI and confirmed it returned 0 records, proving the precision loss.
