# Business Payment Calculator PWA — Custom Edition

## Files
- `index.html` — user interface
- `app.js` — app logic and local data
- `manifest.json` — installable PWA settings
- `service-worker.js` — offline shell cache
- `icon.svg` — app icon

## Deploy to GitHub Pages
1. Download and extract the ZIP.
2. Open your existing GitHub repository `business-payment-calculator` (or your chosen repository).
3. Upload/replace these five files in the repository root. Keep any existing backup files outside the published root if you do not want them public.
4. Commit changes.
5. Go to **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/(root)`.
6. Wait for deployment, then open the HTTPS Pages URL on Android.
7. If the old version persists, close the PWA, open the site in Chrome, reload, then reopen the installed app. The service worker cache name has been updated.

## Default payment formula
- Weight deduction = actual weight × 3.5 kg / 1000, in quintals
- Net weight = actual weight − weight deduction
- Amount after weight deduction = net weight × purchase price per quintal
- Labour = actual weight × ₹25
- Amount after labour = amount after weight deduction − labour
- Percentage deduction = percentage × amount after labour
- Final payment = amount after labour − percentage deduction

The percentage deduction defaults to 1%. You can change global defaults under Menu → Payment formula. A firm can have its own formula.

## Customisation
- Manage firms: add, rename, deactivate/reactivate and configure firm-specific payment formulas.
- Average Price Formula: choose weighted average, simple average, net-weight average, effective payable rate, or a custom numerator/denominator aggregation.
- Materials: add/rename/deactivate material types.
- Custom transaction fields: add text, number or date fields.
- Receipt & appearance: rename the app and set receipt width/footer.
- Backup & recovery: download a full JSON backup, restore a JSON backup, or export CSV.
- Edit and delete saved transactions; filter reports by firm and dates.

## Data and important limitations
- Records are stored locally in the browser on the current device. They do not automatically sync across devices.
- Export a JSON backup regularly and keep a copy somewhere safe. Restoring a backup replaces current app data.
- Clearing browser/site data or uninstalling the PWA may remove locally stored records.
- Existing historical transactions from another installation are not automatically imported. Export a backup from the previous app first if you have records to preserve, then use Restore. This edition uses a versioned local storage key, so the previous app's database will not be silently overwritten.
- This app is designed for one-user, local device use. For shared multi-device data, a server/database would be required.
