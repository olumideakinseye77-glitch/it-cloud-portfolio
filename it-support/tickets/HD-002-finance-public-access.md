# HD-002 — Sales User Could Edit a Finance Document

Date: 22 October 2026
Environment: independent Microsoft 365 lab
Users: Sarah Jones (Finance) and Alex (Sales), both fictional
Status: resolved — operator-confirmed positive and negative access tests
Category: access-control incident

## Requirement

Sarah must be able to edit Finance documents. Alex must not be able to access them.

## Symptoms

The operator created Finance Lab and a Finance Welcome document. Sarah opened, edited and saved the document. When tested as Alex, the document also opened and allowed editing.

## Investigation

The signed-in identity was checked and the operator confirmed Alex. The operator then identified that Finance Lab had been left Public instead of Private. No explicit document grant to Alex had been reported.

Browser session reuse complicated the retest: opening the link used the administrator's session. A separate Chrome Guest window was used to establish Alex's identity.

## Resolution

The operator changed Finance Lab from Public to Private.

## Verification

- Alex's fresh-session test displayed: “You need access” and confirmed the signed-in Alex account did not have access to the item.
- Sarah was then tested separately. The operator confirmed that her access still worked after being asked to edit and save.
- The desired allow/deny behaviour therefore passed in the reported tests.

## Cause and limits

The Public privacy setting was the identified configuration issue, and changing it was followed by successful access restriction. Effective-permission exports, sharing-link inventories and group-membership screenshots were not collected; this record does not claim an independent audit of every access path.

The initial ability to type was reported; a persisted Alex edit before the fix was not separately demonstrated. Private groups do not automatically revoke existing direct grants or sharing links, so membership and document access should still be reviewed.

## Impact and learning

A fictional Sales user had unintended access to a Finance document. No production data or real-world breach is claimed. The exercise demonstrates why permissions need testing as both an authorised and an unauthorised user, and why the browser identity must be verified.

## Evidence basis

Operator confirmations and pasted access-denial text from the guided session. No document contents, passwords or private sharing URLs are included.

## Follow-up

Confirm the final group membership and sharing-link configuration, and capture redacted evidence if needed. The separate planned missing-membership exercise remains unperformed.
