### 🔐 Question Title: Implementing Identity-Based File Access for Remote Teams in Azure

**Question:**
Jordan is a cloud administrator at **BrightOps Solutions**, supporting globally distributed remote teams. As part of the company’s modernization strategy, Jordan is migrating departmental file storage to **Azure Files** and wants to ensure sensitive data is protected — for instance, making sure only the **HR team** can access personnel documents while the **Finance team** sees only budget folders.

What is the most effective way for Jordan to control folder-level access based on **user identity and department roles**?

**A.** Enable **Role-Based Access Control (RBAC)** on the storage account
**B.** Use **Shared Key Authentication** for user access
**C.** Configure **Microsoft Entra Domain Services** for identity-based access
**D.** Restrict access by adding users' IP addresses in **Network Security Group (NSG)** rules

---

**✅ Correct Answer: C**

---

**🧠 Explanation:**
Jordan’s goal is to allow access based on **who the user is** and **what role they have** within BrightOps Solutions. The best solution for this is **Microsoft Entra Domain Services**, which supports **NTFS-like folder-level permissions** on **Azure Files**, enabling true **identity-based access** for mapped drives — just like an on-prem file server.

While **RBAC** (A) controls access to the storage **account** in Azure, it doesn’t apply to **files or folders** inside it. **Shared Key Authentication** (B) is too broad — all users would share the same key and have identical access rights. **NSG rules** (D) limit access by **IP address**, not by **user identity**, and don’t support folder-level control.

That’s why **Option C** is the most secure and suitable approach for organizations like **BrightOps Solutions** that require fine-grained access control.
