# Veloop V6 — GitHub Changes

## 1. Replace the source files
- Replace `src/main.jsx` with the V6 `src/main.jsx` from this ZIP.
- Replace `src/styles.css` with the V6 `src/styles.css` from this ZIP.
- Add `src/assets/public-ad.jpg` if your project keeps local preview assets.

## 2. Ad viewer border effect
The ad image itself is intentionally static. The moving effect is attached to `.viewerFrame` around the viewer:
- `.viewerFrame::before` = sharp travelling dark-blue/cyan/purple border segment.
- `.viewerFrame::after` = soft outer glow.
- `.premiumViewer .modalImg` disables transform/animation so the photo never moves.

## 3. Dashboard first-load sequence
`Dashboard()` is wrapped in `.dashboardPage`.
The CSS uses `nth-child` animation delays so the first page appears in this order:
1. Hero
2. Live reward flow strip
3. Wallet / streak / target / rank stats
4. Wallet / issue / transaction quick actions
5. Daily progress
6. Featured Watch & Earn cards

## 4. Timer
The existing timer already calculates the ring from `time / ad.duration`. V6 keeps the ring synchronized with the countdown and adds a subtle outer pulse only; the ad photo remains still.

## 5. GitHub upload
After replacing the files:
```bash
git add src/main.jsx src/styles.css src/assets/public-ad.jpg
git commit -m "Veloop V6 premium viewer border and dashboard animation"
git push origin main
```

## 6. Vercel
If Vercel is connected to the GitHub repository, a push to `main` should trigger a new deployment. No special rewrite is required for this frontend-only Vite project.

## 7. Important
The Veloop UI is a frontend demo. VE balances/withdrawals are demo credits unless a real backend, authentication, payment provider, server-side validation, and legal/eligibility rules are added.
