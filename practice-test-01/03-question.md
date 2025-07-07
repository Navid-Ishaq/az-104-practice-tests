### 🔐 Question Title: Can Resources Be Moved with Resource Group Locks?

**Question:**

Sarah is a cloud administrator at **AzureNest Technologies**. She deployed a storage account named `azstore100` in the resource group `rg-infra-west`, which currently **has no lock** applied. She now wants to move this storage account to another resource group called `rg-secure-east`, which **has a Delete lock** applied.

Can Sarah complete the move successfully?

**A.** Yes, because the destination lock doesn’t block resource movement  
**B.** No, because Delete locks block incoming resources  
**C.** No, because the source must also have a Delete lock  
**D.** Yes, because resource movement isn’t affected by any lock

---

**✅ Correct Answer: A**

---

**🧠 Explanation:**

In this case, Sarah **can move the storage account** from `rg-infra-west` (no lock) into `rg-secure-east` (Delete lock) because **Delete locks only prevent deletion**, not the addition of new resources.

- A **Delete lock** protects the destination group from accidental deletion but **does not stop adding** resources to it.
- If the **source group had a lock**, like **Read-only**, the move would have failed.
- Since only the **destination group** has a lock and it's a **Delete lock**, the move is **allowed**.

Locks are helpful for protection but do **not block every type of action**. Always check **lock type and placement** before moving Azure resources.

---
---
---
### 🔐 Question Title: Can You Move a Storage Account Between Locked Resource Groups?

**Scenario:**

At **SkyNetCore Ltd.**, a multinational IT firm, engineer **David** is managing Azure resources across two environments: **DevOps** and **Production**. He wants to move a storage account `skyblob001` from one resource group to another for better organization.

Below are the current resource group configurations in each subscription:

#### DevOps Subscription

| Resource Group Name | Region       | Lock Type  |
|---------------------|--------------|------------|
| rg-devops-1         | West Europe  | None       |
| rg-devops-2         | West Europe  | Read-only  |

David has deployed the storage account `skyblob001` into the `rg-devops-1` group.

#### Production Subscription

| Resource Group Name | Region     | Lock Type  |
|---------------------|------------|------------|
| rg-prod-3           | East Asia  | Delete     |
| rg-prod-4           | Central US | None       |

**Question:**  
Can David move the `skyblob001` storage account to the `rg-prod-3` resource group?

**A.** Yes, because Delete locks only prevent deletion, not moves  
**B.** No, because Delete locks block all resource actions  
**C.** No, because the source group is in a different region  
**D.** Yes, but only if the source group also has a Delete lock

---

**✅ Correct Answer: A**

---

**🧠 Explanation:**

Azure’s **Delete lock** stops resources from being **deleted**, but it does **not block moving resources into** that group. The key things to remember:

- The **source group** (`rg-devops-1`) has **no lock**, so resources can be moved out of it.
- The **destination group** (`rg-prod-3`) has a **Delete lock**, which only prevents deletions — not additions or moves.

David can **safely move** the `skyblob001` storage account into the locked `rg-prod-3` group without any problem.

However, if the **source group had a lock** (like Read-only or Delete), that would have **blocked** the move.

