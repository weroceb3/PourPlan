# PourPlan — Vercel deployment package

PourPlan is a static, browser-based restaurant beverage inventory prototype. It uses plain HTML, CSS, and JavaScript in `public/index.html` and has no server-side code, build step, API keys, or database requirement.

## Deploy with GitHub + Vercel

1. Create or sign in to a GitHub account.
2. Create a new repository named `pourplan` (Public is simplest for a class demonstration). Do not add secrets or real business/customer data.
3. Upload the contents of this folder to the repository so the structure is:

   ```text
   pourplan/
   ├── README.md
   └── public/
       └── index.html
   ```

4. Create or sign in to a Vercel account and choose **Add New → Project**.
5. Import the `pourplan` GitHub repository and authorize GitHub access if prompted.
6. In the project configuration, use:
   - Framework Preset: **Other**
   - Root Directory: `./`
   - Build Command: leave blank / override off
   - Install Command: leave blank / override off
   - Output Directory: `public`
   - Environment Variables: none
7. Select **Deploy**. Vercel should publish the static `public/index.html` file and provide a `*.vercel.app` URL.
8. Open the URL in a private/incognito window or a different browser to test it as a new visitor.

## Demonstration instructions

1. Open the published URL.
2. On the Dashboard, select **Load demo data** and confirm if prompted.
3. Explore Dashboard, Beverages, Record sale, Suppliers, and Orders & receipts.
4. To test a sale, open **Record sale**, choose a beverage, enter a quantity, and save. Confirm that on-hand stock decreases.
5. To test replenishment, inspect the supplier's next cutoff/delivery window and the reorder trigger in the Beverages table.
6. To test receiving stock, open a beverage, choose **Create order**, then go to **Orders & receipts** and select **Receive delivery**.

## Important data and privacy note

PourPlan stores its data in the browser's `localStorage`. This means data is saved separately in each visitor's browser and device. Classmates and the instructor can all open the same published URL, but they do not share one inventory dataset, and changes made in one browser are not visible in another. The demo-data button lets each visitor load their own sample dataset. Clearing browser site data or using a different browser/device can remove or make that local data unavailable.

The app does not connect to a point-of-sale system, send purchase orders to suppliers, or use a shared database. No Supabase project or environment variables are needed for this version.

## Updating the published app

After deployment, edit `public/index.html` in the GitHub repository and commit the change. Vercel automatically builds a new deployment from the connected repository. Re-open the public URL and retest the changed feature.
