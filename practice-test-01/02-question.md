### 🚫 Question Title: Can You Move That App?

**Question:**  
Emily is a cloud engineer at **SkyNetCore Technologies**, managing different departments hosted in Azure. She has deployed a web app called `team-hub-app` inside a resource group named `rg-devops-1` located in **North Europe**. She now wants to move it to another resource group called `rg-devops-2` in the same region.

However, `rg-devops-2` has a **Read-Only lock** applied.

What will happen if Emily tries to move the app into the locked resource group?

- **A.** The app will move successfully, and the lock will be applied afterward  
- **B.** The move operation will fail due to the Read-Only lock  
- **C.** The lock will automatically be removed during the move  
- **D.** The app will move, but it will become unavailable until unlocked  

---

**✅ Correct Answer: B**

---

### 🧠 Explanation:

In Azure, a **Read-Only lock** means that **no changes** — including **moves** — can be made to resources within that resource group. Even though the app is currently outside `rg-devops-2`, moving it **into** the locked group is considered a **modification** of that group.

So when Emily tries to move `team-hub-app` into `rg-devops-2`, the action will **fail**.  
To allow the move, the lock must first be **removed** or **disabled** temporarily. Once the move is done, the lock can be re-applied if needed for protection.

This helps prevent accidental changes in sensitive environments, like production or compliance groups.

---
---
---

### 📋 Question Title: Resource Group Locks and App Movement in Azure

**Scenario:**  
SkyNetCore Technologies has two Azure subscriptions — “DevLab” and “ProductionLab.”  
Here are the resource groups in each:

| Subscription    | Resource Group     | Region       | Lock Type   |
|----------------|--------------------|--------------|-------------|
| DevLab         | rg-devops-1        | North Europe | None        |
| DevLab         | rg-devops-2        | North Europe | Read Only   |
| ProductionLab  | rg-prod-1          | East US      | Delete      |
| ProductionLab  | rg-prod-2          | Central US   | None        |

Emily, a cloud admin at SkyNetCore, deployed an app named `team-hub-app` in the `rg-devops-1` group. She now wants to move it to `rg-devops-2`.

**Question:**  
Can Emily move the app into `rg-devops-2` successfully?

- **A.** Yes, the app will move, and the lock will apply afterward  
- **B.** No, the move will fail because of the Read Only lock  
- **C.** Yes, but the app will become locked and unusable  
- **D.** No, because they are in different subscriptions  

---

**✅ Correct Answer: B**

---

### 💡 Explanation:

Emily cannot move the app into `rg-devops-2` because a **Read Only lock** prevents **any changes** to that resource group — and **moving a resource in** is considered a change.  

The correct approach would be to **remove or disable the lock**, perform the move, and **reapply the lock** afterward for safety.

Note: All groups are in the **same subscription and region**, so that’s not the issue here.


