# HD-003 — Sales Access Lost After Membership Removal

Date: 27 October 2026
Status: resolved — operator-confirmed lab result
User: Sarah Jones (fictional)
Type: deliberately introduced access incident

## Working baseline
After her department transfer, Sarah could edit and save Sales Welcome and was denied Finance Welcome.

## Fault and symptom
The operator removed Sarah from Sales Lab membership, saved the change and tested the Sales document in a fresh browser session. When asked whether Sarah received “You need access”, the operator confirmed the denial before confirming the recovery steps.

## Investigation and cause
The controlled change was removal of Sales group membership. The known-good baseline and denied-access test linked that membership to access. This was a known-cause lab exercise, not an unknown production outage.

## Resolution and verification
Sarah was added back as a Sales Lab member. The operator confirmed a fresh-session test restored access and allowed editing and saving the Sales document.

| Stage | Expected | Reported result |
| --- | --- | --- |
| Healthy baseline | Sarah edits Sales | Passed |
| Membership removed | Sarah denied Sales | Passed |
| Membership restored | Sarah edits and saves Sales | Passed |

## Limits
Evidence is the operator's guided-session confirmations. No screenshots, permission export, sign-in logs or measured propagation timing were collected. Finance denial was verified in the prior transfer test; it was not separately retested after this recovery.

## User update
“Your Sales group membership has been restored and document editing has been tested successfully.”

This is an example update, not a message sent to another person.

## Learning
Check group membership and the signed-in identity before changing document permissions. Retest the employee's actual task after the fix.
