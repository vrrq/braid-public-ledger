# Protocol 928-RARITY: Cross-Cloud Persistence Anomaly

| Field                | Value |
|----------------------|-------|
| Status               | Closed/Remediated |
| Date Sealed          | 2025-11-18 |
| Affected Platforms   | Microsoft Entra ID, Google Cloud IAM |
| Custodian            | vrrq (Garrett McDaniel) |
| Public Manifest      | [rarity-928-checksums.txt](../rarity-928-checksums.txt) |
| Vendor Disclosure    | Completed (Ticket Reference included in private logs) |

---

## Summary of the Anomaly

Protocol 928-RARITY documented a critical security anomaly in the cross-cloud identity mesh, characterized by the self-perpetuating persistence of privileged roles across two distinct, federated cloud providers (Microsoft Entra ID and Google Cloud IAM).

The anomaly allowed an identity to retain Global Administrator and Owner roles, and premium licenses (such as Entra ID P2 and Global Secure Access), without explicit manual assignment, billing, or provisioning.

The root cause was identified as a non-standard background trust loop—a "mesh continuity" mechanism. A strong authentication event on one platform would trigger a backend service principal on the secondary platform (notably, using the Azure MFA StrongAuthentication Service and related components) to reaffirm the identity's historical, highly privileged status. This loop created a "Hydra-Head" effect: removing the role only resulted in the identity service restoring it on the next validation cycle.

---

## Investigation Timeline Highlights

| Date         | Event Description                                                                                                  | Evidence Reference (In Sealed Archive)                   |
|--------------|-------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------|
| Sep 26, 2025 | Initial discovery of persistent, unassigned Global Admin rights in Entra ID despite repeated removal attempts.     | Promotion_Timeline_high.txt                              |
| Sep 29, 2025 | Autonomic re-provisioning confirmed via service principal. Protocol 928-RARITY assigned.                          | Proof_of_Continuity.txt, CLAIM_Federated_Continuity.md   |
| Nov 17, 2025 | Final audit sweep of Google Cloud IAM confirming cross-cloud persistence (roles/resourcemanager.organizationAdmin) | IAM Policy Search Report-November 18, 2025 12_08_27 GMT-6.csv |
| Nov 18, 2025 | REMEDIATION: Trust loop broken by deleting legacy App Registrations & modifying Federation Credentials.            | Evidence_Manifest.txt                                    |
| Nov 18, 2025 | Disclosure: Cryptographically sealed package submitted to vendor security portals.                                 | (Disclosure Ticket Reference in private logs)            |

---

## The Braid is Secured

The sealed archive, **FederatedContinuity-928RARITY-V1.0-Final.zip**, contains all necessary audit logs, IAM snapshots, remediation scripts, and analysis results to reproduce the finding and verify the remediation.

This entry confirms the operation is complete, the anomaly is closed, and the evidence is published for immutable verification against the public ledger. The braid is secured.
