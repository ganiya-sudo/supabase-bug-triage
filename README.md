# Open-Source Bug Triage & Verification

This repository contains a log of my technical triage work. I actively monitor open-source platforms (like Supabase) to reproduce reported bugs, verify frontend/database issues, and validate community fixes.

## Reproductions

### Bug 1: SQL Editor Auto-Limit Syntax Error (Issue #51836)
**Status:** Reproduced & Confirmed
**Environment:** Chrome, Windows 11, EU-West region
**The Issue:** When auto-limit is enabled (e.g., 100 rows), writing `LIMIT ALL` or `LIMIT NULL` causes the SQL Editor to append a second `LIMIT 100`, generating invalid SQL (`select 1 limit all limit 100`).
**My Action:** Ran the exact reproduction steps on my end. Confirmed the syntax error and provided environment details to the developer for the fix.
https://github.com/supabase/supabase/issues/51836#issuecomment-6215042957
<img width="1305" height="669" alt="1 Issue #51836" src="https://github.com/user-attachments/assets/88c162b3-b1eb-457a-8330-b4d8a13a1fbb" />
<img width="1271" height="595" alt="Issue #51836" src="https://github.com/user-attachments/assets/c4fd662c-0c39-4e95-96a4-fb1dddd4c9a5" />
<img width="1321" height="633" alt="2 Issue #51836" src="https://github.com/user-attachments/assets/fa8af48a-196d-442a-a973-863d45f16a30" />


### Bug 2: Table Editor Decimal Precision Rounding (Issue #51827)
**Status:** Reproduced & Confirmed
**Environment:** Chrome, Windows 11, EU-West region
**The Issue:** When filtering a high-precision decimal in the Table Editor, the UI rounds the number (due to JavaScript limits), resulting in "0 records" found.
**My Action:** Created a table with the exact decimal `0.123456789012345678901`. Applied the filter in the UI and confirmed it returned 0 records, proving the precision loss.
https://github.com/supabase/supabase/issues/51827#issuecomment-6233371376
<img width="636" height="300" alt="Issue #51827" src="https://github.com/user-attachments/assets/2774b162-4233-42b1-bf45-d7209576beb5" />
<img width="396" height="428" alt="1 Issue #51827" src="https://github.com/user-attachments/assets/7618c9d1-192b-41d1-8b3c-2e127653d7d3" />

