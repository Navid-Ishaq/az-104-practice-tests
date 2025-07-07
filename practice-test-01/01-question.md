### 🔐 Question Title: Implementing Identity-Based File Access for Remote Teams in Azure

**Question:**  
Jordan is a cloud administrator at **BrightOps Solutions**, supporting globally distributed remote teams. As part of the company’s modernization strategy, Jordan is migrating departmental file storage to **Azure Files** and wants to ensure sensitive data is protected — for instance, making sure only the **HR team** can access personnel documents while the **Finance team** sees only budget folders.

What is the most effective way for Jordan to control folder-level access based on **user identity and department roles**?

- **A.** Enable **Role-Based Access Control (RBAC)** on the storage account  
- **B.** Use **Shared Key Authentication** for user access  
- **C.** Configure **Microsoft Entra Domain Services** for identity-based access  
- **D.** Restrict access by adding users' IP addresses in **Network Security Group (NSG)** rules  

---

**✅ Correct Answer: C**

---

### 🧠 Explanation:

Jordan’s goal is to allow access based on **who the user is** and **what role they have** within BrightOps Solutions. The best solution for this is **Microsoft Entra Domain Services**, which supports **NTFS-like folder-level permissions** on **Azure Files**, enabling true **identity-based access** for mapped drives — just like an on-prem file server.

While **RBAC** (Option A) controls access to the **storage account**, it does **not** control access to individual files or folders inside the file share.  
**Shared Key Authentication** (Option B) gives every user the **same access**, making it unsuitable for secure role-based access.  
**NSG rules** (Option D) control **network access** by IP address and cannot enforce user-specific or folder-specific permissions.  

That’s why **Option C** is the most secure and scalable approach for a growing organization like **BrightOps Solutions**.
