# Arknights: Endfield Daily Sign-in Script (Google Apps Script)

This is a **Google Apps Script** that automates the daily sign-in process for **Arknights: Endfield** (SKPORT/Gryphline). It runs automatically on Google's servers, so you don't need to keep your computer on.
This script is working as of March 1st 2026. It can handle accounts with multiple regions, if you play on both Asia and America/Europe like me.

## 🚀 Setup Instructions

### Step 1: Get ACCOUNT_TOKEN

1.  Sign in https://game.skport.com/endfield/sign-in.
2.  Copy the code portion from the json in https://web-api.skport.com/cookie_store/account_token.

---

### Step 2: Install the Script

1.  Go to [script.google.com](https://script.google.com/).
2.  Click **+ New Project**.
3.  Delete any code currently in the editor (e.g., `function myFunction...`).
4.  **Paste** the [script](https://github.com/nano-shino/EndfieldCheckin/blob/main/EndfieldAutoCheckIn.js) into the editor.
5.  At the top of the script, find the configuration section:
    ```javascript
    const ACCOUNT_TOKEN = "";
    ```
6.  Paste your token inside the quotation marks.

---

### Step 3: Setup Discord Notification (Optional)

If you want to receive a notification on Discord when the script runs:

1.  Open **Discord** and go to your server.
2.  Right-click the text channel where you want notifications.
3.  Select **Edit Channel** → **Integrations** → **Webhooks**.
4.  Click **New Webhook**.
6.  Click **Copy Webhook URL**.
7.  Go back to your Google Script and paste the URL in:
    ```javascript
    const DISCORD_WEBHOOK_URL = "";
    ```
---

### Step 4: Activate the Daily Schedule

1.  Save the script (Floppy disk icon or Ctrl+S). Give the project a name (e.g., "Endfield Daily").
2.  In the toolbar dropdown menu (next to "Debug"), select **`setupDailyTrigger`**.
3.  Click **Run**.
4.  **Authorization:**
    - Google will ask for permission to run. Click **Review Permissions**.
    - Select your Google Account.
    - You will likely see a screen saying "Google hasn’t verified this app" (because it's a custom script you just made).
    - Click **Advanced** (bottom left) -> **Go to [Project Name] (unsafe)**.
    - Click **Allow**.
5.  Check the **Execution Log** at the bottom. It should say:
    > _✅ Trigger set! The 'main' function will run daily between 3 AM and 4 AM (UTC+7)._

---

## ❓ FAQ & Troubleshooting

**Q: The script failed with "Token Expired".** A: The `ACCOUNT_TOKEN` may expire after a few weeks or months, or if you log out of the website manually. Simply repeat **Step 1** to get a new token and update the script variable.

**Q: How do I test if it works right now?** A: In the script editor, select the function **`main`** from the dropdown and click **Run**. Check the logs or your Discord channel for the result.

**Q: How do I stop the script?** A: To stop it from running, go to the **Triggers** icon (alarm clock) on the left sidebar of the script editor and delete the trigger listed there.
