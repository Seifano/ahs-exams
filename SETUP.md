# Firebase setup (free plan, about 15 minutes)

You only need a Google account. No billing, no card, no command line.

## 1. Create the project
1. Go to https://console.firebase.google.com and sign in with Google.
2. Click **Create a project** (or **Add project**). Name it `ahs-exams`. Turn Google Analytics **off**. Click **Create project**, then **Continue**.

## 2. Register the website and copy its settings
1. On the project home page, click the **</>** (Web) icon.
2. App nickname: `ahs-exams-site`. Leave "Firebase Hosting" unticked. Click **Register app**.
3. You'll see a code block containing `const firebaseConfig = { apiKey: "...", ... }`. **Copy that whole block and paste it to me in chat.** I'll put it into `firebase-config.json` for you. (These values are safe to share. They identify the project; they aren't passwords.)
4. Click **Continue to console**.

## 3. Turn on logins
1. Left menu → **Build → Authentication** → **Get started**.
2. **Sign-in method** tab → click **Email/Password** → switch on the first toggle → **Save**.
3. **Settings** tab → **Authorized domains** → **Add domain** → type `seifano.github.io` → **Add**.

## 4. Create the database
1. Left menu → **Build → Firestore Database** → **Create database**.
2. Pick a location near your students (e.g. `me-central2` Dammam, or `eur3` Europe). Click **Next**.
3. Choose **Start in production mode** → **Create**.
4. Open the **Rules** tab. Delete everything there, paste the contents of `firebase/firestore.rules`, and click **Publish**.

## 5. Put the site live
Upload `index.html` and the `firebase-config.json` I send back to your `ahs-exams` GitHub repo (replace the old files).

## 6. Make yourself admin
1. Open https://seifano.github.io/ahs-exams/ and **Create account** with your own details.
2. Back in Firebase → **Firestore Database → Data** → `users` → click your document.
3. Click the `role` field's value `Student`, change it to `Admin`, press **Update**.
4. On the site, sign out and sign in again. You'll land on the admin screens.
5. Go to **Questions** → **Copy built-in questions to Firebase** (one time).

Done. Everything else, including new admins and students, is managed from the site's **Accounts** screen.

## Free plan limits
Free Firebase allows about 50,000 reads and 20,000 writes per day, plenty for a school. Uploads are sorted by the app's built-in rules (Claude sorting would need a paid plan).
