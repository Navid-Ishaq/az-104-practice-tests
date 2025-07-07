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
