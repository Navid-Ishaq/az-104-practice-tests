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

---
---
---

### 🔐 Question Title: Setting Up Secure, Role-Based File Access in Azure

**Question:**  
Sarah is an IT administrator at **AzureNest Technologies**, a company with remote teams spread across several countries. She is moving all department files to Azure Files and wants to make sure that only certain team members can view or edit specific folders — like letting only HR see employee records.

Which method should Sarah use to make sure each user gets only the access they need, based on their company login and role?

A. Enable Role-Based Access Control (RBAC) on the storage account  
B. Use Shared Key Authentication for all users  
C. Set up Microsoft Entra Domain Services to control folder-level access  
D. Add each user’s IP address to a network security group rule

---

**✅ Correct Answer: C**

---

**🧠 Explanation:**  
Sarah wants to make sure access is based on **who** the user is — and what they’re allowed to do. That’s where **Microsoft Entra Domain Services** comes in. It allows identity-based access for Azure Files, meaning you can set permissions for folders and files based on a user's role, just like on traditional office file servers.

Options like RBAC (A) are great for controlling *Azure resources* (like who can manage a storage account), but they don’t control access inside the files and folders. Shared Key (B) gives the same access to everyone — no identity check. IP rules (D) restrict based on where someone is connecting from, but not *who* they are. That’s why **Option C** is the smartest and most secure choice here.

---
