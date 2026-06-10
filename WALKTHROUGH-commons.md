# Walkthrough — Commons Only

*how an ordinary space enters angeliaX*

---

ANGX does not require operational work to participate. Anyone with something real and consistent to give enters through the commons log alone.

---

## The people and the space

**Fatima** lives outside Tunis. She runs a small market garden with her sister. Most weeks there is more than the family needs.

**Youssef** lives nearby. He has been coming to the gate for two months. He runs a seasonal olive press. A base in Sfax added his olive press node four months ago. Commons witnessing is unlocked for him.

**Nour** is travelling from Algiers to Tunis.

---

## Part 1 — Fatima

---

### Initializing the client

First run. One question:

*Are you logging work and surplus for a fixed location or for your own work?*

Fatima selects **[ A fixed location ]**. Her keypair is generated. The answer is signed into the first record. Initialize Base is present in her client — greyed out, not yet active.

---

### Registering a commons node

**Commons tab → Register Node**

- **Node Type:** `food`
- **Description:** `Surplus vegetables from market garden. Saturdays 8-11AM. Farm gate on Route de Mornag. Bring a bag.`
- **Location:** Mornag, Tunisia
- **Contact:** her phone number

---

### Logging

She logs every Saturday after the gate closes.

**Signal — operational:** `Gate open. Tomatoes and courgettes. Six people came. All taken.`

**Signal — operational:** `Gate open. Smaller harvest. Tomatoes only. Three people came.`

**Signal — failure:** `No surplus this Saturday. Heat damage to courgette crop. Back next week.`

**Signal — operational:** `Gate open. Tomatoes, peppers, herbs. Eight people came.`

Twelve months. Forty-eight Saturdays. Failures logged alongside the good weeks.

---

### Publishing her library

**Client → Publish Library**

Her library is publicly addressable. One commons node. Forty-eight signals. All signed. All permanent. She shares the address with Youssef.

---

## Part 2 — Witnesses

Youssef has been at the gate. He opens Fatima's food node.

**Commons tab → Fatima's food node → Post Witness Signal**

**Witness signal — operational:** `Gate open as described. Saturdays 8-11AM. Good quantity. Steward present. Consistent over two months.`

A second neighbour witnesses the following month. A person from Tunis who found the library address through a steward in the Sfax collection witnesses the month after.

Three witness signals. All from verified nodes. All from people present at the gate.

---

## Part 3 — The farm initializes as a base

Twelve months of commons logging. Three witness signals from verified nodes across two regions.

The Sfax base steward finds Fatima's library through Youssef's witness signal — Youssef is already in the Sfax collection, and his signal references her node directly. A household base outside Bizerte finds it the same way, through a steward whose feed they hold. Both read the signal history. Both add her food node to their collections independently.

Two distinct verified bases have added a node from this keypair. **Initialize Base activates.**

Fatima clicks **Initialize Base**.

A base keypair is generated on the farm's device. The base is announced on the network. The Base tab activates.

**Base identity:**

- **Name:** farm-mornag
- **Description:** `Small market garden outside Tunis. Saturday surplus. Gate open to anyone.`
- **Location:** Mornag, Tunisia

---

### Partnering with Sfax

The Sfax base steward has read twelve months of Fatima's signals and added her node to their collection. Both stewards exchange base addresses.

One base proposes. The other accepts. Both sides log the event independently. Both base keypairs sign the handshake entry.

farm-mornag is now a verified base. Its collection is traversable through the partner chain.

---

### Curating

People have been coming to the gate for a year. Fatima knows who they are and what they do.

Youssef runs an olive press two kilometres away. September to December, he presses for anyone who brings olives. No charge. Fatima has been there. She has seen it operating.

**Client → Add to Base** — Youssef's olive press commons node.

A woman from the next village runs a free health consultation from her home on Wednesday mornings. She has been doing it for three years. Fatima has attended twice. Her node has six months of signals and two witnesses.

**Client → Add to Base** — her informational commons node.

Two nodes. Both observed directly. Both added to farm-mornag's public collection.

Every base in the partner chain can now reach Youssef's olive press and the Wednesday health consultation through farm-mornag. Fatima did not build those provisions. She observed them, judged them real, and made them reachable.

That is what the base holds — not just Fatima's surplus, but the honest record of what is actually happening in that area, curated by someone who was there.

---

## Part 4 — Someone finds the gate

Nour is travelling from Algiers to Tunis. Someone in Algiers gave her the Sfax base address. She connects her client to it and queries.

**Commons tab → query: food**

Two nodes appear:

- One registered eight months ago. No signals after the second week.
- **Fatima's node:** forty-eight signals over twelve months. Three witnesses. Last signal four days ago.

Nour reads the log. One failure in six weeks, logged honestly. Last Saturday was good. It is Friday evening. She adjusts her route.

Saturday morning. Nour arrives at the gate at half past eight. Fatima is there. Tomatoes, courgettes, herbs.

Nour takes what she needs. She has a commons node of her own — a room in Algiers, logged for two years. She shares her library address before leaving.

---

## What remained

Fatima started with surplus vegetables and a gate.

Over twelve months:

- She logged forty-eight Saturdays, including failures
- Three people witnessed her provision directly
- Two independent bases added her node to their collections
- Her farm initialized as a base
- A partner handshake with Sfax made it a verified base in the partner chain
- She curated two local provisions into the base collection — both observed directly
- A stranger arrived because the signal history was real

No operational log. No builder network. No infrastructure project.

Surplus, stated precisely, logged honestly, witnessed by people who were there. A local gate becomes queryable infrastructure. What is real in one place becomes reachable everywhere the partner chain runs.

---

*ANGX — Operational Log + Commons Log*
