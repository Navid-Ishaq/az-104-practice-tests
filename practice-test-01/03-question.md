### 📦 Question Title: Can a Locked Resource Group Block a Resource Move?

**Question:**
David works at **CloudBridge Systems**, a global company with teams in different regions.  
He has deployed a storage account called `hrdata-store` inside a resource group named `rg-dev-1`.  
Now, he wants to move this storage account into another group, `rg-prod-3`, which has a **Delete lock** applied.  

What will happen if David tries to move the resource?

- **A.** The move will succeed because a Delete lock only blocks deletion, not movement  
- **B.** The move will fail because the destination group is locked  
- **C.** The move will succeed but the lock will be removed during transfer  
- **D.** The move will fail because resources can't move across regions  

---

**✅ Correct Answer: B**

---

### 💡 Explanation:

In Azure, **locks are designed to protect resource groups from changes**. A **Delete lock** doesn't just stop deletion — it also **prevents adding or moving resources into the group**.  

In David’s case, `rg-prod-3` has a Delete lock, so Azure will **block the move** of `hrdata-store` to protect that group from accidental changes.  

To complete the move, David would need to temporarily remove the lock, move the resource, and then reapply the lock after the move.

---
---
---
### 📦 Question Title: Moving a Resource into a Locked Group — Can It Work?

---

**Background Scenario:**

Emily is a cloud engineer at **AzureNest Technologies**.  
Her company has two Azure subscriptions: `DevOps` and `Production`.

Here are the **resource groups** in each subscription:

#### DevOps Subscription

| Name         | Region       | Lock Type |
|--------------|--------------|-----------|
| rg-dev-1     | West Europe  | None      |
| rg-dev-2     | West Europe  | Read-only |

#### Production Subscription

| Name         | Region    | Lock Type |
|--------------|-----------|-----------|
| rg-prod-3    | East Asia | Delete    |
| rg-prod-4    | Central US| None      |

Emily has deployed a storage account called **`wzstorage`** in the `rg-dev-1` group.  
Now, she wants to move it to the `rg-prod-3` group in the `Production` subscription.

---

**Question:**  
Can Emily move `wzstorage` to the `rg-prod-3` resource group?

- **A.** Yes, because locks only affect deletions, not moves  
- **B.** Yes, as long as both resource groups are in Azure  
- **C.** No, because the target group has a **Delete lock**  
- **D.** No, because the resource is in a different subscription  

---

**✅ Correct Answer: C**

---

### 💡 Explanation:

Although a **Delete lock** sounds like it only blocks deletion, in Azure it also prevents **moving** resources **into** the locked group. This is to protect production workloads from unexpected changes.  

Emily would first need to **remove the Delete lock** from `rg-prod-3`, then move the storage account, and finally reapply the lock to keep protections in place.

This ensures that production environments stay stable unless an intentional update is made.

