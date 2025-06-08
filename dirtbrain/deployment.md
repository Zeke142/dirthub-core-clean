## ✅ GitHub → Vercel Trigger Rules

1. **Production builds must originate from a `stable-*` branch**
   - Ex: `stable-tailwindfix`, `stable-v4-ready`
   - Avoid deploying directly from `main`

2. **Default branch on GitHub must match Vercel's configured production branch**
   - Change under GitHub Settings → Branches

3. **Do not rely on Vercel remembering last branch/commit**
   - Always confirm deploy log includes:
     ```
     Cloning github.com/[user]/[repo] (Branch: [expected], Commit: [expected])
     ```

4. **If Vercel deploy fails to update despite commits being visible:**
   - Delete project on Vercel
   - Re-import GitHub repo
   - Set production branch explicitly

5. **Deployments from `main` are never assumed stable**
   - Only `stable-*` branches get promoted to primary domain
