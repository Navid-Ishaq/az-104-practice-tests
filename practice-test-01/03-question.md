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
### 🔐 Question Title: Can You Move Azure Resources with Locks Applied?

**Scenario:**

Sarah, a cloud engineer at **AzureNest Technologies**, wants to reorganize some Azure resources. She has a storage account named `azstore100` currently placed in a resource group with no lock. She wants to move it to another resource group that has a **Delete lock** applied.

Here’s the setup:

| Resource Group Name | Region       | Lock Type  |
|---------------------|--------------|------------|
| `rg-infra-west`     | West Europe  | None       |
| `rg-secure-east`    | East US      | Delete     |

**Question:**  
Can Sarah move the storage account `azstore100` from `rg-infra-west` to `rg-secure-east`?

**A.** Yes, because a Delete lock on the destination group does not block the move  
**B.** No, because Delete locks stop incoming resources  
**C.** No, because the source group must also have a lock  
**D.** Yes, because locks don’t affect moves at all

---

**✅ Correct Answer: A**

---

**🧠 Explanation:**

In Azure, a **Delete lock** only prevents resources in the group from being **deleted**. It does **not stop new resources** from being **added** or **moved into** that group.

Since:
- The **source group** (`rg-infra-west`) has **no lock**, and  
- The **destination group** (`rg-secure-east`) has a **Delete lock**,  

👉 Sarah **can successfully move** the resource to the new group.

⚠️ **Important Note:**  
If the **source** group had a **Read-only** or **Delete** lock, the move would have **failed**. Lock behavior always depends on what action you're performing and **where the lock is applied**.



