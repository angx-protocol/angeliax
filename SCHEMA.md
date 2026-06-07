# angeliaX (ANGX) — Schema & Specification

*May 2026*

---

## Terms

**steward** — a builder running one or more operational or commons nodes.

**base steward** — a person operating a base. Curates its collection. Decides which feeds are accepted.

**base** — a persistent curated collection belonging to a physical space. Independent keypair. Stays when stewards rotate.

**witness** — a steward who directly observed or replicated another node's work and recorded what they found.

**library** — a publicly addressable collection of a keypair's own nodes and replicated feeds. Anyone with the address can read it. Both steward keypairs and space keypairs publish libraries.

---

## Two Logs

**Operational Log** — the operational reality of work. What is being built, tested, failed, learned. The node is the specific project or practice.

**Commons Log** — standing provisions only. What a node regularly and freely gives. The node is the specific provision.

Same client. Same keypair. Structurally separate.

---

## Technical Stack

| Component  | Role                                                                                     |
| ---------- | ---------------------------------------------------------------------------------------- |
| Hypercore  | Append-only, cryptographically signed feed. One feed per node. Immutable.                |
| Hyperbee   | B-tree index over Hypercore. Queries by node type, location, signal type, timestamp.     |
| Hyperswarm | Peer discovery via DHT. No central servers.                                              |
| Hyperdrive | File storage attached to a node. Attachments fetched on demand. Max 10MB per attachment. |

Recommended hardware for running a base: Raspberry Pi + UPS. Individual builders may run the client on any laptop.

---

## Operational Log — Registration

| Field       | Status    | Description                                                                           |
| ----------- | --------- | ------------------------------------------------------------------------------------- |
| Node ID     | Automatic | 256-bit value derived from keypair. 64-character hex string. Never changes.           |
| Node Type   | Mandatory | Single selection. Immutable.                                                          |
| Description | Mandatory | One sentence. What is currently being built or tested. Max 120 characters. Immutable. |
| Location    | Mandatory | Free text. Max 64 characters.                                                         |
| Contact     | Optional  | Free text. Max 64 characters.                                                         |

### Node Type Enum — Operational

| Type         | Field                                                             |
| ------------ | ----------------------------------------------------------------- |
| food         | Food production, preservation, distribution infrastructure        |
| water        | Water access, purification, storage, distribution systems         |
| shelter      | Housing construction, materials, spatial infrastructure methods   |
| health       | Healthcare delivery, medical devices, public health systems       |
| energy       | Energy generation, storage, distribution, off-grid systems        |
| connectivity | Communications hardware, protocols, mesh/satellite infrastructure |
| other        | Fundamental infrastructure work not covered above.                |

Operational nodes cover practical and theoretical work within the enum. Learning signals with attached documentation are the primary mechanism for theoretical work.

The enum is intentionally minimal and stable. Evaluate nodes by primary function, not surface label — sanitation maps to health, transportation to connectivity, educational infrastructure to informational or the relevant domain. Use `other` only when the work genuinely cannot be mapped to an existing category.

---

## Operational Log — Steward Signal

| Field       | Status    | Description                                                                                                     |
| ----------- | --------- | --------------------------------------------------------------------------------------------------------------- |
| Signal ID   | Automatic | Unique identifier. Used by witnesses to reference a specific claim.                                             |
| Node ID     | Automatic | The posting node's identifier.                                                                                  |
| Timestamp   | Automatic | Immutable.                                                                                                      |
| Signal Type | Mandatory | operational / failure / learning / retired                                                                      |
| Message     | Mandatory | Max 120 characters. Factual. Present tense. Learning signals may include attached documentation via Hyperdrive. |

| Signal      | Meaning                                                                     | Example                                                                     |
| ----------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| operational | Work progressing as intended.                                               | *Filtration prototype stable. Flow rate consistent across 48hr test.*       |
| failure     | Work cannot progress or method has failed.                                  | *Membrane clogged at 72hrs. Prototype three failed.*                        |
| learning    | Something confirmed through direct experience or replication worth sharing. | *Ceramic blend confirmed. 8hrs continuous. Method documented and attached.* |
| retired     | Work permanently done.                                                      | *Project closed. Logs remain public.*                                       |

The retired signal accepts one optional field: `successor_node_id` — pointing to the node this work has evolved into. The link is one-way and part of the permanent record.

---

## Operational Log — Witness Signal

Posted by any steward who directly observed or replicated another node's work. Requires a verified operational node — at least one own operational node accepted into a verified base's collection. A base is verified if it has at least one active partner handshake. Commons-only stewards cannot post operational witness signals. Witnessing is competence-gated: the witness has done comparable work and can assess what they observed.

| Field             | Status    | Description                                               |
| ----------------- | --------- | --------------------------------------------------------- |
| Witness Node ID   | Automatic | The witnessing node's identifier.                         |
| Timestamp         | Automatic | Immutable.                                                |
| Observed Node ID  | Automatic | The node being witnessed.                                 |
| Referenced Signal | Optional  | The specific steward signal being engaged with.           |
| Signal Type       | Mandatory | Chosen independently by the witness.                      |
| Message           | Mandatory | Max 120 characters. What was directly observed or tested. |

| Signal      | Meaning                                                         | Example                                                    |
| ----------- | --------------------------------------------------------------- | ---------------------------------------------------------- |
| operational | Observed the work functioning as described.                     | *Filter running. Flow rate confirmed. Steward present.*    |
| failure     | Observed the work failing or not as described.                  | *Lab empty. No steward contact in five days.*              |
| learning    | Directly replicated a method. Result confirmed or contradicted. | *Replicated in Kampala. Flow within 5% of Nairobi result.* |
| retired     | Directly observed permanent closure.                            | *Lab cleared. Equipment donated. Confirmed by steward.*    |

---

## Commons Log — Registration

| Field       | Status    | Description                                                                            |
| ----------- | --------- | -------------------------------------------------------------------------------------- |
| Node ID     | Automatic | 256-bit value derived from keypair. 64-character hex string.                           |
| Node Type   | Mandatory | Single selection. Immutable.                                                           |
| Description | Mandatory | One sentence. What is provided, when, at what capacity. Max 120 characters. Immutable. |
| Location    | Mandatory | Free text. Max 64 characters. Immutable.                                               |
| Contact     | Optional  | Free text. Max 64 characters.                                                          |

### Node Type Enum — Commons

| Type          | Provision                                                                |
| ------------- | ------------------------------------------------------------------------ |
| food          | Free food, meals, produce                                                |
| water         | Free water access, filtration, distribution                              |
| shelter       | Free accommodation, workspace                                            |
| health        | Free health services, consultations, medicine                            |
| energy        | Free energy access, charging, off-grid provision                         |
| connectivity  | Free connectivity, wifi, mesh, satellite                                 |
| informational | Free knowledge, consultation, legal aid, translation, technical guidance |
| other         | Any fundamental surplus provision not covered above.                     |

---

## Commons Log — Steward Signal

| Field       | Status    | Description                                 |
| ----------- | --------- | ------------------------------------------- |
| Signal ID   | Automatic | Unique identifier.                          |
| Node ID     | Automatic | The posting node's identifier.              |
| Timestamp   | Automatic | Immutable.                                  |
| Signal Type | Mandatory | operational / failure / learning / retired  |
| Message     | Mandatory | Max 120 characters. Factual. Present tense. |

| Signal      | Meaning                                 | Example                                                                    |
| ----------- | --------------------------------------- | -------------------------------------------------------------------------- |
| operational | Provision being fulfilled as described. | *Breakfast running. Five people served. Supplies stable.*                  |
| failure     | Provision cannot be met.                | *No supplies. Suspended this week. Back Monday.*                           |
| learning    | Something discovered worth sharing.     | *Batch cooking confirmed. Waste down 40%. Method documented and attached.* |
| retired     | Provision permanently ended.            | *Breakfast ended permanently. Final day March 31st.*                       |

---

## Commons Log — Witness Signal

Requires any verified node — at least one own node of any type accepted into a verified base's collection. Commons witnessing is presence-gated: any accountable steward who directly received or observed the provision may witness it. No commons node of the same type required.

| Field             | Status    | Description                                                 |
| ----------------- | --------- | ----------------------------------------------------------- |
| Witness Node ID   | Automatic | The witnessing node's identifier.                           |
| Timestamp         | Automatic | Immutable.                                                  |
| Observed Node ID  | Automatic | The commons node being witnessed.                           |
| Referenced Signal | Optional  | The specific steward signal being responded to.             |
| Signal Type       | Mandatory | operational / failure / learning / retired                  |
| Message           | Mandatory | Max 120 characters. What was directly observed or received. |

| Signal      | Meaning                                       | Example                                                          |
| ----------- | --------------------------------------------- | ---------------------------------------------------------------- |
| operational | Directly received the provision as described. | *Breakfast was there. Exactly as logged. Seven people.*          |
| failure     | Provision not available as described.         | *No breakfast. Kitchen locked.*                                  |
| learning    | Observed a method worth the network knowing.  | *Batch cooking confirmed. Applied in our space. Waste down 35%.* |
| retired     | Directly observed permanent end of provision. | *Space closed. Provision ended.*                                 |

The retired signal on a commons node accepts one optional field: `successor_node_id` — the node ID of the provision that continues what this node provided.

---

## Content Persistence

Learning signal attachments are stored in the node's Hyperdrive. Textual signals replicate automatically. Attachments are fetched on demand — retrieved explicitly when a steward or base requests them.

---

## Library

Any keypair publishes a library to make its work visible and evaluable before entering the network. The library has two sections: own nodes — all nodes signed by this keypair — and replicated nodes — feeds the keypair holds from others. Both sections are publicly addressable under a single p2p address derived from the keypair.

Publishing a library is a unilateral act. No permission required. The library updates automatically as the keypair logs and replicates. No name, no description, no separate identity. The keypair is the library's identity.

A library is distinct from a base. A base belongs to a physical space and stays when stewards rotate. A library belongs to a keypair.

---

## Querying

Querying operates within a connected base or library. No global search. Discovery is base to base through the partner chain, or directly through a steward's library address.

Operational nodes queryable by: node type, location, signal type, timestamp, witness activity, steward-to-witness ratio, referenced signal.

Commons nodes queryable by: node type, location, signal type, timestamp, witness activity.

---

## Integrity

| Mechanism                | How It Works                                                                                                                                                                                                                                                                |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 120-character constraint | Forces factual, present-tense reporting.                                                                                                                                                                                                                                    |
| Signal type enum         | No category for opinion, suggestion, or commentary.                                                                                                                                                                                                                         |
| Two independent streams  | Steward and witness feeds are separate. Contradictions permanently visible.                                                                                                                                                                                                 |
| Append-only log          | Nothing deleted or edited. All entries cryptographically signed.                                                                                                                                                                                                            |
| Witness verification     | Operational witnessing requires a verified operational node. Commons witnessing requires any verified node. Operational witnessing is competence-gated. Commons witnessing is presence-gated. Base steward judgment at the curation decision is the primary integrity gate. |
| Visible silence          | Empty nodes and witness-only nodes are visible anomalies.                                                                                                                                                                                                                   |
| Referenced signals       | All witnesses to a specific claim queryable together.                                                                                                                                                                                                                       |

---

## Open Questions

- **Library tab UX.** Whether the library is surfaced as a separate tab or through Settings. To be resolved with developers against the running client.
- **Library address resolution.** Whether the library announces itself on Hyperswarm under a key derivable from the steward keypair or via another mechanism. To be resolved with developers.

---

## Base

A base is a persistent curated collection belonging to a physical space. Independent keypair. Stays when stewards rotate. Distinct from a library — a library belongs to a steward, a base belongs to a place.

Three components: **identity**, **collection**, **partners**.

---

### Base Identity

| Field       | Status    | Description                                                       |
| ----------- | --------- | ----------------------------------------------------------------- |
| Base ID     | Automatic | 256-bit value derived from base keypair. 64-character hex string. |
| Public Key  | Automatic | Discovery key. Shared to enable connection via Hyperswarm.        |
| Name        | Optional  | Free text. Max 64 characters.                                     |
| Description | Optional  | One sentence. Max 120 characters.                                 |
| Location    | Mandatory | Free text. Max 64 characters.                                     |
| Contact     | Optional  | Free text. Max 64 characters.                                     |
| Initialised | Automatic | Timestamp. Immutable.                                             |

Viewing the collection is open to anyone with the public key. Entry is curated.

---

### Collection Log

Appended to the base feed. Signed by the base keypair. Permanent.

| Field     | Status    | Description                      |
| --------- | --------- | -------------------------------- |
| Entry ID  | Automatic | Unique identifier.               |
| Base ID   | Automatic | The base recording the decision. |
| Timestamp | Automatic | Immutable.                       |
| Node ID   | Automatic | The node being added or removed. |
| Action    | Automatic | added / removed                  |

| Action  | Meaning                                                                                     |
| ------- | ------------------------------------------------------------------------------------------- |
| added   | Node is now part of the public collection. Reachable through the base address.              |
| removed | Node is no longer in the public collection. Previously replicated copies persist elsewhere. |

Curation is node-level. Base stewards add or remove specific nodes, not entire keypairs. Adding a node requires no consent from its steward.

---

### Partner Log

Appended to the base feed. Signed by both base keypairs. Permanent.

| Field              | Status    | Description                            |
| ------------------ | --------- | -------------------------------------- |
| Handshake ID       | Automatic | Unique identifier.                     |
| Initiating Base ID | Automatic | The base that proposed the connection. |
| Receiving Base ID  | Automatic | The base that accepted.                |
| Timestamp          | Automatic | Timestamp of acceptance. Immutable.    |
| Partner Public Key | Automatic | Public key of the partner base.        |

One base proposes. The other accepts. Both sides log the event independently. Collections become traversable through the partner chain. Both base stewards stake their collection's credibility on the decision.

---

### Base Actions

**Replicate** — base steward holds a copy of the feed locally. Not yet in the public collection. Steward observes signal activity, witness corroborations, learning signals before deciding.

**Add to base** — node enters the public collection. Logged, signed, permanent.

**Remove** — node leaves the public collection. Previously replicated copies persist elsewhere.

---

### Client Type Declaration

On first run, before any nodes are created, the client asks one question:

*Are you logging work and surplus for a fixed location or for your own work?*

**[ A fixed location ]** — somewhere that stays. A hostel, clinic, farm, lab, workshop, seedbank, household. Initialize Base is present in this client.

**[ My own work ]** — a practice, research, or project that moves with the steward. Initialize Base is never present in this client.

The answer is signed into the keypair's first record. Shapes one UI branch only. The protocol sees only keypairs and nodes after this point. Space clients should run on a persistent device from first run — the keypair generated at initialization is permanent and belongs to the space.

---

### Initialization Threshold

A space client may initialize a base when two distinct verified bases have each added at least one node owned by this keypair to their public collections. A verified base has at least one active partner handshake in its Partner Log.

The client detects this condition by scanning Collection Logs from bases it has contact with. When the threshold is met, Initialize Base activates. No message is sent. No approval is requested.

The threshold applies to whatever verified bases exist at the time. The first base initializes without prior verified bases existing. The second requires confirmation from the first. From the third onward, two confirmations are required.

---

### Base — Open Questions

- **Multiple base stewards.** Any authorized steward can add or remove nodes independently. Partnership establishment and dissolution requires agreement by all authorized stewards on both sides. Exact mechanics depend on Autobase implementation.
- **Query scope.** Local query returns results from the base's own collection. Federated query extends through the partner chain. Manual traversal moves base by base. To be resolved with developers.
- **Partner replication strategy.** Full replication, sparse on demand, or per-partner choice. To be resolved with developers.
- **Base keypair derivation.** Generated independently of the steward keypair on the persistent device at the location. Exact derivation mechanic to be resolved with developers.
- **Initialize Base trigger synchronization.** Client detects two added entries from two distinct verified bases pointing to nodes owned by this keypair. How this count synchronizes across devices when confirmations arrive independently — to be resolved with developers.

---

*ANGX — Schema & Specification — May 2026*
