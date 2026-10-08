# Petsa De Peligro — subscription edition

Your customers open a personal link, tap **Install**, and start logging. There's no password and no setup for them. You run everything from one Google Sheet (your **tracker**).

This is completely separate from your own household app. Nothing there changes.

---

## What's in the folder

| File | Where it goes |
|---|---|
| `index.html`, `manifest.json`, `service-worker.js`, `icons/` | A **new** GitHub repository (the app customers open) |
| `Code.gs` | Apps Script inside your **tracker** Google Sheet |
| `README.md` | This guide (you can upload it to GitHub too) |

---

## One-time setup (about 20 minutes)

### Step 1 — Put the app on GitHub

1. On github.com, tap **+** → **New repository**. Name it `petsa` and set it to **Public**. Tap **Create repository**.
2. Tap **uploading an existing file**. Drag in `index.html`, `manifest.json`, `service-worker.js` and the whole `icons` folder. Tap **Commit changes**.
3. Go to **Settings → Pages**. Under *Branch* choose **main** and **/(root)**, then tap **Save**.
4. Wait 1–2 minutes and refresh. Copy the link it shows, e.g. `https://yourname.github.io/petsa/`. This is your **App link**.

### Step 2 — Create your tracker sheet

1. Go to sheets.google.com and create a **blank** spreadsheet. Name it **Petsa De Peligro – Tracker**.
2. Menu **Extensions → Apps Script**.
3. Delete everything in the code box, paste **all** of `Code.gs`, and tap **Save** (the disk icon).
4. In the toolbar dropdown next to **Run**, choose **setupTracker**, then tap **Run**.
5. Google asks for permission. Tap **Review permissions** → choose your account → **Advanced** → **Go to … (unsafe)** → **Allow**.
   *This is your own script. It needs Sheets and Drive so it can create one spreadsheet per customer.*
6. Back in the sheet, you'll see new tabs: **Customers, Subscription_Payments, App_Settings, Admin_Log**. A folder **Petsa De Peligro – Customers** is also created in your Google Drive.

### Step 3 — Turn on the server (Web app)

1. In Apps Script, tap **Deploy → New deployment**.
2. Tap the gear ⚙ next to *Select type* → **Web app**.
3. **Execute as:** *Me*. **Who has access:** *Anyone*. Tap **Deploy**.
4. Copy the **Web app URL** (it ends with `/exec`). This is your **Web app link**.

### Step 4 — Fill in your settings

1. Go back to the tracker sheet and **refresh the page**. A **Petsa De Peligro** menu appears at the top.
2. **Petsa De Peligro → Open admin panel → Settings** tab. Fill in:
   - **App link**: from Step 1
   - **Web app link**: from Step 3
   - **GCash name and number** (and Maya if you have one)
   - **Where customers message you**: your Facebook page, email or mobile number
   - Prices are already **₱79/month** and **₱699/year**, with a **14-day** free trial and **3 grace days**. Change them any time.
3. Tap **Save settings**. The yellow "Finish setting up" box disappears when everything's ready.

---

## Everyday use

### New customer

1. **Admin panel → ＋ Add customer**. Type their name (email and mobile are optional). Tap **Create account**.
2. Wait about 20–40 seconds while their private spreadsheet is created.
3. Tap **Copy message** and send it to them (Messenger, Viber, SMS, email).
   **Copy it right away.** For security, the link isn't saved anywhere. If it gets lost, use **New link**.

The customer opens the link → taps **Install** → a **guided setup** starts by itself, one question at a time. It must be finished the first time.

1. Their name
2. **How many incomes they receive** (1–6). Then, for each income: type and name, how often (monthly, twice a month, weekly, every 2 weeks), which day, how much, and what happens on weekends
3. Which bills they pay (tap from a list or add their own), then the amount and due day for each
4. **Their monthly budget**: the total for bills + daily needs. The app shows what their bills alone add up to and suggests amounts.
5. **"Are you saving for something?"** If yes: pick an idea (Emergency fund, Christmas, Travel, Phone…) or type their own, with an amount and an optional date. The app checks it right away: **Possible ✓, put in ₱X a month**, or **Not possible by that date**, with the date it *would* be possible and how much more per month they'd need.
6. How much money they have right now
7. A review screen, then **"You're all set!"**: expected income, monthly budget, what's left to save and their goal check, plus the next paydays and due dates

Everything starts from **today**, so nothing shows as overdue on day one. Afterwards, customers can **edit their own income, bills and budget anytime**, just like your household app. They can also run the guided setup again from the dashboard or Settings.

### What's in the app for your customers

Simple words everywhere: **Fixed bills** (not "recurring"), **Spending**, **Bills paid**, "Late" instead of "Overdue". Every board has a one-line explanation of what it shows.

- **Home**: their money status, **Safe to spend**, six simple numbers (Budget this month, Spent so far, Left in budget, Bills to pay, Money in, Money left), their goals, and bills to pay first
- **Savings**: how much they kept each month and in total
- **Goals**: "You can save about ₱X a month" (regular income − budget), each goal with a progress bar and an honest verdict (possible / not possible + when), plus **Put money in / Take out**. Money in a goal is set aside, so it no longer counts as safe to spend. Six goal ideas are sized to their own budget.
- **Ask**: type a question in English or Taglish ("Magkano pa pwede kong gastusin?", "Can I afford ₱2,000?", "When is my next payday?", "How much did I spend on groceries?", "Who owes me money?"). Answers come only from their own numbers, with a short "how we got this". It's not a general AI, and it says so politely for other topics.
- **Calculator**: a simple calculator plus quick checks: Can I afford it?, How long to save?, Split a bill, Daily allowance

### The phone lock

Each account works on a limited number of phones: **2 by default** (Admin panel → Settings → *Phones per account*).

- The first phones that open the link take the places. Opening the app again on the same phone doesn't use another place.
- An extra phone sees **"This account is already used on 2 phones"** with your contact details, and can't see or change anything.
- **Edit** on a customer shows each phone (e.g. "Android · Chrome · app") with first and last use. Tap **Remove** to free one place, or **Reset all phones**.
- **Phones allowed** in Edit gives one customer more places (for example 4 for a Family plan). Leave it blank to use the default.
- A phone that hasn't opened the app for 60 days frees its place automatically.
- **New link** also clears all phones.
- iPhone: when they follow the install steps, the **Copy my link first** button keeps Safari and the home-screen app counted as the **same** phone.

### Customer paid you

1. They send GCash or Maya and message you the reference number.
2. **Admin panel → ₱ Payment** on their row → choose **Monthly**, **Yearly** or **Custom days** → type the reference → **Save payment**.
3. Their access is extended. Paying early never loses days: the new month or year starts after their current end date, or after the free trial.
4. Their app unlocks on its own within a minute, or right away when they tap **I've paid — check again**.

### What customers see

| Situation | In their app |
|---|---|
| Free trial | Blue banner: "Free trial · 12 days left" + How to subscribe |
| Paid, ending within 5 days | Reminder banner to renew |
| Past due (grace days) | "Payment due" banner. The app still works. |
| Expired | Renew screen with your prices, GCash/Maya numbers and instructions. **Their data is kept.** |
| Paused by you | "Your account is paused" |

### Other buttons

- **New link**: the old link stops working immediately, and their phone list is cleared. Use it when a customer lost their link or shared it with someone outside their household. Their data stays.
- **Edit**: fix their name or phone, change dates by hand, **Pause / Un-pause**, or **Erase data** (a backup copy is saved to your Drive first).
- **Sheet**: opens that customer's spreadsheet.
- **Payments** tab: every payment with reference numbers. The top shows how much you received this month.
- **Phones** column: places used out of allowed, e.g. "2 / 2" (highlighted when full).

You can also type a date straight into the **Customers** sheet (e.g. `paidUntil`). The app picks it up within a minute.

---

## Updating later

- **App screens** (`index.html`): upload the new file to GitHub, replacing the old one. Customers get it the next time they open the app.
- **Server** (`Code.gs`): paste the new code, **Save**, then **Deploy → Manage deployments → ✏️ Edit → Version: New version → Deploy**.
  Always edit the existing deployment. A *New deployment* creates a different Web app link, and every customer's link would stop working.

---

## Lost or new phone

- **New phone, old one still works or was sold:** if all places are used, the new phone shows the phone-limit screen. Open **Edit** → **Remove** the old phone, then they tap **Try again**.
- **Phone lost or stolen:** tap **New link** and send it. The lost phone is locked out, all places are freed, and their data is safe.

The welcome message already tells customers to save their link for this.

## Good to know

- **Each customer has their own spreadsheet** in your Drive folder. One customer can never see another's data.
- **The link is the key.** Anyone with it can open that account, like a shared Netflix login. Couples can share it on purpose (the app has **Settings → Copy my link** for a second phone).
- **iPhone:** home-screen apps are kept separate from Safari, so iPhone users paste their link once after installing. The app tells them how and has a **Copy my link** button.
- **Switching accounts on one phone:** if someone opens a different person's link, the app removes the previous account's data from that phone first. It's never mixed.
- **No time triggers needed.** Each customer's bills and income for the coming months are generated the first time they open the app each day.
- **Size limits:** everything runs on your Google account's free daily allowance. That's comfortable for roughly the first 50–100 customers. If saves start feeling slow beyond that, it's time to move to a database like Supabase (your subscribers can pay for it by then).
- **Privacy:** you're holding people's financial information. Keep the tracker and the Customers folder private (don't share them). Before launching publicly, add a short privacy policy and terms; the Philippine Data Privacy Act applies. *This isn't legal advice, so check with a lawyer for the final wording.*

## Troubleshooting

| Problem | Fix |
|---|---|
| No **Petsa De Peligro** menu | Refresh the sheet. Still missing → Apps Script → run `setupTracker` again, then refresh. |
| "Paste your Web app link first" | Settings → Web app link (Deploy → Manage deployments → copy the `/exec` URL). |
| Customer says "This link no longer works" | You made a New link. Send them the newest one. They can paste it in **Settings → Got a new link?** |
| Paid but still locked | Check the Payments tab. Ask them to tap **I've paid — check again**. |
| Customer sheet creation is slow | Normal: 20–40 seconds. Don't close the panel while it works. |

---
