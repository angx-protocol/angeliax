# Walkthrough

*how angeliaX (ANGX) works*

---

ANGX is two honest logs. One records what is actually being built, tested, learned, and failed. The other records what is freely and consistently provided. Both are append-only, cryptographically signed, and permanent.

---

## The people and the space

**Amara** lives in Nairobi. Eight months developing a low-cost ceramic water filter for high-sediment water. She runs two commons nodes alongside her operational work — a weekly consultation and a rooftop food garden.

**David** lives in Kampala. Four months developing rainwater harvesting systems for informal settlements. He runs a free tool library for builders in his area. Travelling to Nairobi for two weeks.

**The Nairobi space** is a colive and cowork space for builders. The manager logs the space's commons provisions on a dedicated device and curates feeds from builders passing through.

Any space with a persistent device and a committed steward can run a base — a clinic, a farm, a school, a lab, a household.

---

## Part 1 — Amara

---

### Initializing the client

First run. One question:

*Are you logging work and surplus for a fixed location or for your own work?*

Amara selects **[ My own work ]**. Her keypair is generated. The answer is signed into the first record. Initialize Base never appears in her client.

---

### Registering her operational node

**Operational tab → Register Node**

- **Node Type:** `water`
- **Description:** `Developing low-cost ceramic water filter for high-sediment river water.`
- **Location:** Nairobi, Kenya
- **Contact:** her Signal username

The client generates a Node ID — a 64-character hex string derived from her keypair. No signals yet.

---

### Logging

**Operational tab → her node → Post Signal**

**Signal 1 — operational:** `Ceramic filter prototype four assembled. Testing flow rate in high-sediment water from Nairobi River this week.`

**Signal 2 — failure:** `Local ceramic supplier inconsistent porosity. Flow rate 40% below minimum viable. Switching to composite material.`

**Signal 3 — learning:** `Composite ceramic blend confirmed. Filters high-sediment water 8hrs continuous.`

She attaches documentation to the learning signal. The 120-character signal is the pointer. The full method is in the attachment, fetched on demand.

---

### Registering commons nodes

**Commons tab → Register Node**

**Commons node — informational:**

- **Node Type:** `informational`
- **Description:** `Free water filtration consultation. Two hours weekly. Wednesdays 2-4PM.`
- **Location:** Mathare, Nairobi
- **Contact:** her Signal username

**Signal — operational:** `Consultation running. Two builders this week. Filter design and material sourcing covered.`

**Commons node — food:**

- **Node Type:** `food`
- **Description:** `Surplus vegetables from rooftop garden. Fridays after 5PM. Gate on Mwangi Street. First come.`
- **Location:** Mathare, Nairobi

**Signal — operational:** `Garden producing well. Surplus tomatoes and kale available this Friday.`

---

### Publishing her library

Eight months of operational signals, failures, learnings. Two commons nodes with consistent signal history.

**Client → Publish Library**

Her library is publicly addressable under a single p2p address. Two sections: own nodes — her water node, informational node, food node, all signed by her keypair — and replicated nodes — feeds she holds from others. Updates automatically. Belongs to her. Moves with her.

She shares her library address with the Nairobi space manager.

---

## Part 2 — The Space

---

### Initializing the client

First run on the space's dedicated device — a Raspberry Pi. One question:

*Are you logging work and surplus for a fixed location or for your own work?*

The manager selects **[ A fixed location ]**. His keypair is generated. Initialize Base is present in this client — greyed out, not yet active.

---

### Logging the space

The space logs commons provision.

**Commons node — shelter:**

- **Node Type:** `shelter`
- **Description:** `Free one-week stay for two builders with active operational log. Contact via Signal.`
- **Location:** Nairobi, Kenya
- **Contact:** his Signal username

**Signal — operational:** `Two builders in residence. Both logging actively. Space stable.`

**Signal — operational:** `One builder departed. Slot open from Monday. Contact to arrange.`

**Commons node — food:**

- **Node Type:** `food`
- **Description:** `Shared kitchen. Breakfast available weekdays 7-9AM. Capacity five.`
- **Location:** Nairobi, Kenya

**Signal — operational:** `Breakfast running. Four builders this week. Supplies stable.`

**Signal — failure:** `No breakfast Thursday and Friday, low stocks. Back Monday.`

---

### Publishing the library — eight months of commons provision

Eight months of consistent commons logging. Shelter node, food node.

**Client → Publish Library**

The library is publicly addressable. Over eight months, builders from across Africa, Europe, and the Americas have stayed at the space, used the commons, and posted witness signals. The witness record is dense — nineteen signals from verified stewards in different regions, all confirming the shelter and food nodes are real and operating as logged.

A farm base in Java, Indonesia and a clinic base in Kampala, Uganda independently discover the Nairobi space through a shared library address. Both read the witness record. Nineteen signals from verified stewards across three continents — geographically diverse, consistent over time, each signed by a keypair with its own operational or commons history. Neither base steward has visited Nairobi. The witness record is sufficient. Both independently add the Nairobi shelter commons node to their collections.

Two distinct verified bases have each added a node owned by this keypair. The client scans their Collection Logs, detects both additions, confirms both bases have active partner handshakes. **Initialize Base activates.**

---

### Initializing the base

The manager clicks **Initialize Base**.

A base keypair is generated on the device — independent of the manager's steward keypair. The base is announced on the network. The Base tab activates.

From this moment the device holds its own identity, independent of any individual steward. The manager can rotate out. The base stays.

**Base identity:**

- **Name:** origin-nairobi
- **Description:** `Colive and cowork space for builders in East Africa.`
- **Location:** Nairobi, Kenya

---

### Observing and curating

Builders pass through and share their library addresses. The manager replicates their feeds locally — holds copies on the device, reads silently.

**Client → Replicate** — feed held locally. Not in the public collection.

Signal activity, witness corroborations, learning signals. Time. No algorithm decides.

Amara's library address came in shortly after the base was initialized. The manager visits her lab, observes the filter running, and attends the consultation. Eight months of operational signals, two witnesses from nodes with substantial history, a learning signal with full documentation. He adds her nodes to the base collection.

**Client → Add to Base**

Amara's water node, informational node, and food node are now part of the base's public collection. Logged, signed, permanent.

Amara's client detects this — a verified base has added her nodes. Her keypair now has verified status. **Operational and commons witnessing unlock.**

---

### Partnering with another base

The Java farm base steward — one of the two who added the Nairobi shelter node and triggered initialization — has observed the Nairobi base's collection record over time. Both stewards exchange base addresses.

One base proposes. The other accepts. Both sides log the event independently. Both base keypairs sign the handshake entry.

Collections become traversable through the partner chain. Amara's water node — accepted in Nairobi — is now reachable through the Java base, and through that base's partners, further still.

---

## Part 3 — David

---

### Connecting from Kampala

David is still in Kampala. A builder passing through gave him the Nairobi base address. He connects his client.

The base collection is readable by anyone with the address. David queries it.

**Commons tab → query: shelter**

The shelter commons node appears. Free one-week stay — active operational log required. David has four months of logged rainwater harvesting work. He qualifies. He messages the manager and arranges his stay.

**Operational tab → query: water nodes**

Three nodes appear:

- One empty — registered, never logged.
- One with two witness signals from nodes with no operational history — a visible anomaly.
- **Amara's node:** four operational signals, two failures, three learnings. Two witness signals from nodes with substantial history.

He opens Amara's node. Reads the full log. Fetches the attached documentation.

He has not met Amara yet. He already knows what she built, what failed, and what she confirmed.

---

### David's nodes — status on arrival

David arrives in Nairobi. He has two nodes of his own:

- **Operational — water:** `Rainwater harvesting system for household use in Kampala informal settlements.` Four months of signals.
- **Commons — informational:** `Free tool library for builders. Available by arrangement. Kampala, Uganda.` Two months of signals, three witness signals from builders who borrowed tools.

No verified base has added either node yet. His witness buttons are disabled.

---

### The manager adds David's nodes

David has been at the space for several days. The manager has worked alongside him, seen how he operates, read four months of rainwater work and two months of commons logging. Three witness signals from verified Kampala stewards are already on his commons node — builders who borrowed tools and logged what they found. The manager has not visited Kampala. He makes the admission decision based on David's presence at the space, his feed history, and the existing witness record from stewards who were there.

**Client → Add to Base** — David's operational water node.

**Client → Add to Base** — David's commons informational node.

Both nodes are now in the base's public collection. David's client detects both additions — a verified base has added an operational node and a commons node from his keypair.

**Operational witnessing unlocks. Commons witnessing unlocks.**

---

### Replicating Amara's method

David brings ceramic material from Kampala to Amara's lab. He runs her method. It works. After 72 hours of continuous use without cleaning, output drops 60%. Amara's documentation flags cleaning but not the degradation rate or its timeline.

David observed the full replication. He opens Amara's water node.

**Operational tab → Amara's water node → Post Witness Signal**

**Witness signal — operational:** `Filter running as described. Flow rate confirmed. Setup replicable. Steward present.`

**Witness signal — learning** *(referenced to her learning signal):* `Replicated composite blend using Kampala materials. Flow rate within 5% of Nairobi result. Method transfers across material source.`

**Witness signal — failure** *(referenced to her learning signal):* `Output degrades 60% after 72hr continuous use without cleaning. Not flagged in original documentation. Critical for field deployment.`

Each signal is signed by David's keypair, appended to his own feed, referencing Amara's node ID and the specific signal where relevant.

The failure signal is a direct contradiction of her learning signal. Amara reads it. She posts a new signal on her own node:

**Steward signal — learning:** `Cleaning interval critical. 72hr max before significant output degradation. Updated method and interval table attached.`

The log now holds: original claim, independent replication, honest contradiction, steward response. Permanent. No gatekeeper. No review cycle.

---

### David uses and witnesses the commons

**Wednesday**

David found Amara's informational node in the base. He messages her on Signal. He arrives at her lab at two.

Two hours. David's replication findings, Amara's field notes. Both leave with more than they came with.

David has a verified commons node. Commons witnessing is presence-gated — he received the provision directly.

**Commons tab → Amara's informational node → Post Witness Signal**

**Witness signal — operational:** `Consultation delivered as described. Two hours. Specific, practical, field-relevant. Expertise in ceramic filtration confirmed.`

**Friday**

David walks to the gate on Mwangi Street. Amara is there. He takes vegetables.

**Commons tab → Amara's food node → Post Witness Signal**

**Witness signal — operational:** `Surplus vegetables at gate as described. Good quantity. Steward present.`

---

## What remained

David arrived with a base address and four months of logged work.

In two weeks:

- He found a shelter commons node and arranged a stay before leaving Kampala
- He found a water node in the base and read eight months of documented method before arriving
- His nodes were added to the base collection — operational and commons witnessing unlocked
- He replicated a method and documented a contradiction that updated the original documentation
- He received a commons consultation and witnessed it
- He received food from a rooftop garden and witnessed it
- Both steward feeds and both witness feeds grew — permanently, without any central authority involved

All of it signed. All of it permanent. Reachable by any steward connected to the base or any base partnered with it.

---

*ANGX — Operational Log + Commons Log*
