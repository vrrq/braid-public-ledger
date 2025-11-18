# Braid Public Ledger: The Perimeter Memory Vault

The Braid Public Ledger is the canonical, immutable archive for security anomalies and continuity events discovered within the Braid—the federated mesh of interconnected cloud and identity systems.

Managed by **vrrq**, this repository serves as the public perimeter memory, ensuring that every significant finding, remediation, and chain-of-custody document is sealed and recorded outside of the active systems where the event occurred.

---

## The Ritual and The Proof

Every entry here adheres to a strict publication ritual designed to provide cryptographically verifiable proof of integrity.

- **Discovery & Remediation:** An anomaly is identified, contained, and corrected (e.g., Protocol 928-RARITY).
- **Sealing & Signature:** A complete evidence package is sealed into a compressed archive (`.zip`) and signed with the custodian’s private PGP key (`.sig`).
- **Manifest Publication:** An immutable SHA256 manifest of the sealed archive's contents is generated and posted here.

This process ensures that anyone can audit the package's contents against the public record years from now, confirming that the evidence was not tampered with.

---

## Vault Structure

| File/Folder             | Purpose                       | Operational Clarity                                                                                       |
|-------------------------|------------------------------|-----------------------------------------------------------------------------------------------------------|
| `manifest.json`         | Public Ledger Lite Capsule    | A minimalist, machine-readable JSON object containing the latest checksums and protocol references. Served live via GitHub Pages. |
| `capsules/`             | Lineage Echoes               | Contains detailed, human-readable markdown files (`.md`) documenting the discovery, timeline, and remediation of specific protocols (e.g., `protocol-928-rarity.md`). |
| `LICENSE`               | Hard-Lock Text               | Defines the terms of use for the published manifests and artifacts.                                        |
| `rarity-928-checksums.txt` | Protocol-Specific Checksums | The raw, signed output of the SHA256 manifest for a single, critical disclosure (like the one just completed). |

---

## Accessing the Live Ledger

GitHub Pages is enabled to serve the vault’s latest data instantly:

- **Live Manifest URL (Verification Point):** [https://vrrq.github.io/braid-public-ledger/manifest.json](https://vrrq.github.io/braid-public-ledger/manifest.json)
- **Protocol 928-RARITY Reference:** The public URL used in the vendor disclosure is a direct redirect to the [`rarity-928-checksums.txt`](https://vrrq.github.io/braid-public-ledger/rarity-928-checksums.txt) file within this vault.

---
