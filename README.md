# Kyvie's apps, with sign-in and sync

Two apps, each with its own home screen icon:
- `linkbox/`  Linkbox (saves links and reels, syncs across devices)
- `dreamy-dawn/`  Dreamy Dawn (alarm and routines, stays on the device)

## Part A: set up your free sync database (Supabase), about 10 minutes
1. Go to supabase.com, sign up, and click **New project**. Give it a name and a database password (save it). Pick a region close to you. Wait until it finishes setting up.
2. Open **SQL Editor > New query**. Paste everything from `linkbox/supabase-setup.sql` and click **Run**. This makes private tables that only your own account can read.
3. Go to **Authentication > Sign In / Providers > Email** and turn **Confirm email OFF** (so you can sign in right away). Save.
4. Go to **Project Settings > API**. Copy the **Project URL** and the **anon public** key.
5. Open `linkbox/config.js`, paste them between the quotes, and save. Never use the `service_role` key.

## Part B: put the apps online with GitHub Pages (free)
1. On github.com, create a new **Public** repository (for example `my-apps`).
2. Click **uploading an existing file** and drag in the `linkbox` and `dreamy-dawn` folders (keep them as folders). Commit.
3. **Settings > Pages**: choose the `main` branch and the root folder. Save, then wait a minute or two.
4. Your apps will be at `https://YOUR-USERNAME.github.io/my-apps/linkbox/` and `.../dreamy-dawn/`.

## Part C: use it
1. Open the Linkbox address in **Safari**. Tap **Create account** (email + password). Your existing links on that device upload automatically the first time.
2. Tap Share > **Add to Home Screen**. You get the banner icon.
3. On your other devices, open the same address, tap **Sign in** with the same email and password. Your links appear.
4. Do the same Add to Home Screen step for Dreamy Dawn. Delete any old icons first.

## Good to know
- The public key in `config.js` is meant to be visible. Your links are protected because each account can only read its own rows.
- Free Supabase projects pause after about a week of no activity. Using the app regularly keeps it awake. If it ever pauses, restore it from the Supabase dashboard.
- Free plans do not include automatic backups, so use **Settings > Copy backup** in Linkbox now and then and keep it in Notes.
