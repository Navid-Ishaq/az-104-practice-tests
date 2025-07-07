### 📦 Question Title: App Service Move Blocked Due to Existing Resources

**Question:**

Sarah is a cloud engineer at **SkyNetCore**, where two Azure subscriptions are used — one for staging and another for production.

She has deployed a web app (`app-skynet`) in the staging subscription, inside the resource group `rg-sky-staging-1`.

Now she wants to move this app to the production subscription, specifically into `rg-sky-prod-4`.

However, she notices that another app called `app-prodweb` already exists in `rg-sky-prod-4`.

Based on this setup, can she move the app to the destination resource group?

**A.** Yes, as long as the region is the same  
**B.** Yes, if both groups have no locks  
**C.** No, because the destination group already contains an App Service resource  
**D.** No, unless the app is stopped before moving  

---

**✅ Correct Answer: C**

---

### 🧠 Explanation:

Sarah cannot move her app to `rg-sky-prod-4` **because it already contains another App Service resource** (`app-prodweb`).  
According to **Microsoft Learn**, when moving an **App Service resource across subscriptions**, the **destination resource group must be empty of App Service-related items**.  

These include:
- Web Apps  
- App Service Plans  
- TLS/SSL certificates  
- App Service Environments  

Even if there are **no locks** and both resource groups are in the same **region**, the move is blocked if any App Service resource is already present in the target group.  

That’s why **Option C** is correct — and the move will be denied unless the destination group is empty of App Service components.

---
---
---

### 🧭 Question Title: Moving App Service Resources Across Subscriptions — Blocked by Existing Web App

**Scenario:**

Emily, an Azure administrator at **CloudBridge Systems**, is managing two Azure subscriptions: **DevZone** and **LiveOps**.  
She deployed a web app (`app-devcore`) and its App Service Plan (`ASP-devgrp1-ab1x`) inside a resource group in the DevZone subscription.  
Now, she plans to move this app to another resource group in the LiveOps subscription.

Here is the current setup of both subscriptions:

#### DevZone Subscription Resource Groups

| Name            | Region       | Lock Type |
|-----------------|--------------|-----------|
| rg-devzone-1    | West Europe  | None      |
| rg-devzone-2    | West Europe  | Read-only |

`app-devcore` is hosted in `rg-devzone-1`.

---

#### LiveOps Subscription Resource Groups

| Name             | Region      | Lock Type |
|------------------|-------------|-----------|
| rg-liveops-3     | East Asia   | Delete    |
| rg-liveops-4     | Central US  | None      |

The target group `rg-liveops-4` already contains another web app called `app-liveweb`.

---

**Question:**

Can Emily move the app service resources (`app-devcore`) from `rg-devzone-1` to `rg-liveops-4`?

**A.** Yes, because both groups have no locks  
**B.** Yes, if the app is stopped before moving  
**C.** No, because the destination already has an App Service resource  
**D.** No, unless the region is identical in both groups

---

**✅ Correct Answer: C**

---

### 🧠 Explanation:

According to **Microsoft Learn**, when you're moving App Service resources **across subscriptions**, the **destination resource group must not contain any App Service resources** — such as web apps, App Service Plans, or imported SSL certificates.

In this case, since `rg-liveops-4` already contains `app-liveweb`, the move is blocked — even though:
- No locks are present
- Regions could be valid
- The app is running or stopped

This restriction ensures App Service resources don’t conflict or overwrite each other during cross-subscription moves.  
That’s why **Option C** is correct.

---
