# 🚦 Deployment Triggers – GitHub → Vercel

This module governs how DirtHub safely deploys builds using GitHub and Vercel, including branching strategy, trigger validation, and deployment hygiene.

---

## ✅ Deployment Rules

### 1. **Branch Strategy**
- `main` is a working/dev branch only
- `stable-*` branches (e.g. `stable-tailwindfix`, `stable-v4-ready`) are promoted for production
- `prod` branch may be used for locked public-facing releases

### 2. **GitHub Default Branch**
- The GitHub default branch must match Vercel’s production branch
- Always change this in GitHub → Settings → Branches before importing to Vercel

### 3. **Production Builds Must Use Stable Branches**
- Vercel deployments must originate from `stable-*` branches
- Do not deploy from `main` unless debugging

---

## 🔁 Trigger Validation

### 4. **Deployment Verification**
After any push:
- Confirm the Vercel deploy log contains:
