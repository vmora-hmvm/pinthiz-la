# PINTHIZ.LA — OWNER'S MANUAL
## A Beginner's Guide to Managing Your Website

Created by Victoria for Steph 💙💛
Last updated: July 23, 2026

---

## TABLE OF CONTENTS
1. Getting Started — Your GitHub Account
2. How to View Your Website
3. How to Make Changes (Step by Step)
4. Adding a New Pin/Product
5. Removing a Pin/Product
6. Changing Prices
7. Adding a Discount/Promo Code
8. Managing Raffles
9. Updating Shipping Info
10. Updating FAQ
11. Changing Photos (Founder, Gallery, Birthday)
12. Payment Setup (Venmo, Zelle, Stripe)
13. Updating Instagram Links
14. Updating the Game Schedule
15. What NOT to Touch
16. Troubleshooting

---

## 1. GETTING STARTED — YOUR GITHUB ACCOUNT

Your website lives on GitHub. Think of GitHub as a free file storage that automatically publishes your website to the internet.

### Your account info:
- Website URL: https://vmora-hmvm.github.io/pinthiz-la/
- GitHub login: github.com (ask Victoria for login details)
- Repository name: pinthiz-la

### How to log in:
1. Open your web browser (Chrome, Safari, etc.)
2. Go to https://github.com
3. Enter your username and password
4. You should see a repository called "pinthiz-la"
5. Click on it

---

## 2. HOW TO VIEW YOUR WEBSITE

Your live website is always at:
### https://vmora-hmvm.github.io/pinthiz-la/

Bookmark this on your phone and computer. Anyone can visit this link — it's public.

When you make changes (see below), it takes about 30-60 seconds for the website to update. Refresh your browser to see changes.

---

## 3. HOW TO MAKE CHANGES (STEP BY STEP)

All your website content is in ONE file called `index.html`. This is the only file you need to edit.

### Step 1: Open the file
1. Log into GitHub
2. Click on the "pinthiz-la" repository
3. You'll see a list of files — click on `index.html`
4. You'll see the code for your website (it's long — that's normal)

### Step 2: Edit the file
1. Click the **pencil icon** (✏️) in the top right corner of the code view
2. This opens the editor — you can now type changes

### Step 3: Save your changes
1. Scroll down to the "Commit changes" section
2. In the first box, type a short description of what you changed (example: "Added new Shohei pin")
3. Click the green **"Commit changes"** button
4. Wait 30-60 seconds, then refresh your website to see the changes

### Important: Always make a backup first!
Before making big changes, copy all the code (Ctrl+A to select all, Ctrl+C to copy) and paste it into a text file on your computer (Notepad on PC, TextEdit on Mac). Save it as "pinthiz-backup.html". If something breaks, you can paste it back.

---

## 4. ADDING A NEW PIN/PRODUCT

### Step 1: Upload your pin image
Before adding a product, you need an image URL for it. Ask Victoria to upload the image — she has a system that creates a permanent URL for each image. You'll get a link that looks like:
`https://media.base44.com/files/public/.../your-pin-name.png`

### Step 2: Find the product list
1. Open `index.html` on GitHub
2. Press Ctrl+F (or Cmd+F on Mac) to search
3. Type: `const PRODUCTS = [`
4. You'll see a list of products. Each one looks like this:

```
{id:1,name:"World Champions LA Pin",cat:"pin",price:12,img:"https://media.base44.com/files/public/.../A_00.png",caption:"Monsters Inc LA Pin",desc:"A premium Dodgers-themed enamel pin, hand-designed for true LA fans. Vivid colors, clean detail.",featured:true},
```

### Step 3: Add your new product
Scroll to the END of the product list (look for the closing `];`). Add a new line BEFORE the `];`:

```
{id:71,name:"Your Pin Name",cat:"pin",price:12,img:"YOUR_IMAGE_URL_HERE",caption:"Short Name",desc:"Your description here.",featured:false},
```

### What each part means:
- `id:71` — Use the next number after the last product (if the last one is 70, use 71)
- `name:"Your Pin Name"` — The full name customers see
- `cat:"pin"` — Category. Options: "pin", "sticker", "shirt", "patch"
- `price:12` — Price in dollars (just the number, no $)
- `img:"URL"` — Your image URL from Step 1
- `caption:"Short Name"` — A shorter name for quick display
- `desc:"Description"` — A sentence describing the product
- `featured:false` — Use `true` if you want it in the top carousel, `false` for grid only

### Step 4: Save
Scroll down, type "Added new pin" in the commit message, click "Commit changes".

---

## 5. REMOVING A PIN/PRODUCT

### Step 1: Find the product
1. Open `index.html` on GitHub
2. Press Ctrl+F and search for the product name (e.g., "Hello Kitty")
3. You'll find the line with that product

### Step 2: Delete it
1. Delete the ENTIRE line — from `{id:` to the `},` at the end
2. Be careful not to delete any other lines
3. Make sure you don't leave an extra comma or missing comma

### Step 3: Save
Commit changes with message "Removed [product name]".

### Alternative: Hide instead of delete
If you just want to temporarily remove a product but keep it for later, change `price:12` to `price:0` — products with price 0 won't show. Or ask Victoria to help.

---

## 6. CHANGING PRICES

### Step 1: Find the product
1. Open `index.html`
2. Press Ctrl+F, search for the product name
3. Find the `price:12` part of that product's line

### Step 2: Change the price
Change the number. For example:
- `price:12` → `price:15` (to change from $12 to $15)

### Step 3: Save
Commit with message "Updated price for [product name]".

### To change ALL pins at once:
Ask Victoria for help with this — it requires a find-and-replace that can be tricky.

---

## 7. ADDING A DISCOUNT/PROMO CODE

Currently, your site doesn't have a built-in discount code system. Here are two options:

### Option A: Simple discount (Recommended for beginners)
Add a visible promo banner at the top of the shop section:

1. Find `<!-- ===== SHOP ===== -->` in the code
2. Right after `<div class="wrap">`, add this:

```html
<div style="background:linear-gradient(135deg,var(--gold),var(--gold-bright));color:var(--navy);padding:12px 20px;border-radius:12px;text-align:center;font-weight:700;margin-bottom:24px;">
  🎉 USE CODE "LA323" FOR 15% OFF YOUR ORDER — APPLIED AT CHECKOUT
</div>
```

3. Then manually apply the discount when someone pays via Venmo/Zelle (since checkout is manual)

### Option B: Actual working discount code
This requires adding JavaScript for a promo code input in the cart. Ask Victoria to set this up — it involves:
- Adding a text input in the cart drawer
- Adding JavaScript to validate the code and calculate the discount
- Testing the discount calculation

For now, Option A works great since you process payments manually through Venmo/Zelle.

---

## 8. MANAGING RAFFLES

### Your raffle section has:
- A spinning wheel (decorative — just for fun)
- An entry form where people enter name, email, quantity
- Pricing: 1 entry = $5, 3 = $12, 5 = $20, 10 = $35

### To change raffle pricing:
1. Search for: `const prices = {1: 5, 3: 12, 5: 20, 10: 35}`
2. Change the numbers. For example, to make 1 entry = $10:
   `const prices = {1: 10, 3: 25, 5: 40, 10: 70}`
3. There are TWO places this appears — search for both and change both!

### To update raffle text (title, description):
1. Search for: `Grand Slam Giveaway`
2. Change the title text and description text around it

### To change raffle prize info:
1. Search for: `raffle-stat` — you'll see entries count and days remaining
2. Update the numbers and text as needed

### To change the wheel segment text:
1. Search for: `const prizes = ['ENTER', 'WIN', 'GIVE', 'AWAY'`
2. Change the words in the array. Example:
   `const prizes = ['WIN', 'BIG', 'ENTER', 'NOW', 'WIN', 'BIG', 'ENTER', 'NOW']`
3. Keep exactly 8 items in the array (one for each wheel segment)

### Important: The raffle wheel spin is DECORATIVE
When someone enters the raffle, their entry gets added to the cart. The actual raffle drawing happens on Instagram — you manually pick a winner. The wheel is just for visual fun.

### To announce a winner:
1. Post on Instagram Story
2. Update the "Updates" section on the website (see below)

### To update the Updates/Blog section:
1. Search for: `<!-- ===== UPDATES ===== -->`
2. You'll see update cards with badges, titles, dates, and text
3. Edit the text or add a new card by copying an existing card's HTML and changing the content

---

## 9. UPDATING SHIPPING INFO

### To change shipping rates or policies:
1. Search for: `<!-- ===== SHIPPING ===== -->`
2. You'll see four expandable cards:
   - US Shipping
   - International
   - LA Local Pickup
   - Stadium Pickup

3. Each card has text inside `<p>` tags. Edit the text between `<p>` and `</p>`

### Example: Changing US shipping from $4.99 to $5.99
Find: `Flat-rate $4.99 anywhere in the US`
Change to: `Flat-rate $5.99 anywhere in the US`

### To change the free shipping threshold:
Find: `Free shipping on orders over $40`
Change the $40 to whatever you want.

### To add or remove a shipping card:
Copy an entire `<div class="ship-compact-card">...</div>` block to add a new one, or delete a block to remove one. Ask Victoria if this is confusing.

---

## 10. UPDATING FAQ

### To edit an existing FAQ:
1. Search for: `<!-- ===== FAQ ===== -->`
2. Each FAQ item looks like this:

```html
<div class="faq-item" onclick="toggleFaq(this)">
  <div class="faq-q">How long until my order ships? <span class="icon">...</span></div>
  <div class="faq-a"><p>Your answer text here.</p></div>
</div>
```

3. Change the question text inside `faq-q` and the answer inside `faq-a`

### To add a new FAQ:
Copy an entire `<div class="faq-item">...</div>` block, paste it after the last one, and change the question and answer.

---

## 11. CHANGING PHOTOS

### Founder photo (Story section):
1. Search for: `alt="Steph G. — founder of pinthiz.la"`
2. Replace the image URL in `src="..."` with your new image URL
3. There may be TWO references to this image (one in the background overlay) — update both

### Gallery photos (Community Gallery):
1. Search for: `gallery-grid` or `gallery-item`
2. Each gallery image has its own URL in `src="..."`
3. Replace URLs to swap images

### Birthday photos:
1. Search for: `bday-slide`
2. Each slide has an image URL in `src="..."`
3. Replace with new photo URLs

### Raffle background image:
1. Search for: `raffle{position:relative;background:`
2. Replace the image URL in the CSS

### Hero background:
1. Search for: `hero-bg{position:absolute`
2. Replace the image URL

### Important: All image URLs must start with `https://media.base44.com/...`
If you need new images uploaded, ask Victoria — she has a system to create permanent URLs for images.

---

## 12. PAYMENT SETUP

### Venmo
1. Search for: `@Stephie33`
2. This appears in the checkout function AND in the FAQ
3. Replace with your new Venmo handle if it ever changes

### Zelle
1. Search for: `gstephanie3@yahoo.com`
2. This appears in the checkout function AND in the FAQ
3. Replace with your new Zelle email if it ever changes

### Stripe (Card Payments)
Currently, Stripe checkout shows a popup alert saying "Stripe integration coming soon." To make real Stripe payments work:

1. Create a Stripe account at https://stripe.com (if you don't have one)
2. Once approved, ask Victoria to set up the Stripe integration
3. Victoria will:
   - Create backend functions that connect to Stripe
   - Replace the alert popup with a real Stripe checkout redirect
   - Test it with a small purchase

For now, Venmo and Zelle work perfectly. Most customers pay via Venmo anyway.

### How checkout currently works:
When a customer clicks "Venmo" in the cart:
1. A popup appears saying "Redirecting to Venmo @Stephie33 — Total: $XX"
2. The customer manually opens Venmo and sends payment
3. They include their order in the Venmo note
4. You receive the payment and fulfill the order

This is a manual process but works great for a small business.

---

## 13. UPDATING INSTAGRAM LINKS

Your Instagram handle appears in multiple places. To update it everywhere:

1. Search for: `pinthiz.la`
2. Replace with your new handle (without the @)
3. Look for all instances — it appears in:
   - Nav bar
   - Promo section
   - Story section ("Follow @pinthiz.la" button)
   - Footer (Instagram button)
   - FAQ (answer about following)
   - Updates section

### Full Instagram URL format:
`https://www.instagram.com/pinthiz.la/`

If your handle changes to "@pinthizla" (without the dot), you'd update it to:
`https://www.instagram.com/pinthizla/`

---

## 14. UPDATING THE GAME SCHEDULE

### To update upcoming games:
1. Search for: `<!-- ===== UPCOMING GAMES ===== -->`
2. The games load automatically from a JavaScript function
3. If games aren't loading, they may be hardcoded — look for game cards with dates

### To change the "On Deck" text or description:
1. Find `<span class="label">On Deck</span>`
2. Change "On Deck" to whatever you want
3. Find the `<p>` tag below it and change the description

### To manually add games:
If the auto-loading isn't working, you can add game cards manually. Ask Victoria for help with this — it involves copying a card template and filling in team names, dates, and times.

---

## 15. WHAT NOT TO TOUCH

These are parts of the code that control how the website WORKS. Changing them could break things:

### Do NOT change:
- Anything inside `<style>` tags (the CSS) — unless you know CSS
- The JavaScript functions: `addToCart()`, `checkout()`, `renderProducts()`, `toggleCart()`
- The `<script>` section at the bottom
- The `<head>` section (meta tags, font links)
- Class names like `class="product-card"` or `class="cart-drawer"`
- Any `id="..."` attributes

### Safe to change:
- Text content (product names, descriptions, FAQ questions/answers)
- Image URLs (in `src="..."`)
- Prices (the number in `price:12`)
- Instagram handle
- Venmo handle and Zelle email
- Shipping text
- Raffle text and pricing numbers
- Section titles and descriptions

### If you accidentally break something:
1. Don't panic!
2. Go to GitHub → pinthiz-la repository
3. Click "Commits" (the clock icon)
4. Find your last change and click "Undo" or "Revert"
5. Or ask Victoria to restore from backup

---

## 16. TROUBLESHOOTING

### "My changes aren't showing up"
- Wait 60 seconds and refresh again (GitHub Pages has a cache)
- Try a hard refresh: Ctrl+Shift+R (PC) or Cmd+Shift+R (Mac)
- On mobile, close the browser completely and reopen

### "The website is broken / looks wrong"
- You probably accidentally deleted a character or tag
- Go to GitHub → Commits → revert to the last working version
- Or ask Victoria to fix it

### "A product image isn't showing"
- Check the image URL starts with `https://media.base44.com/...`
- Make sure there are no spaces in the URL
- Make sure the URL is inside quotation marks: `img:"URL"`

### "The cart isn't working"
- This is JavaScript — don't try to fix it yourself
- Ask Victoria to check the cart functions

### "Search isn't finding products"
- Make sure product names don't have weird characters
- Search works on `name` and `caption` fields only

### "Mobile layout looks off"
- Don't try to fix CSS yourself unless you know CSS
- Ask Victoria to adjust the responsive styles

---

## QUICK REFERENCE CHEAT SHEET

| Task | Search for this text | What to change |
|------|---------------------|----------------|
| Add product | `const PRODUCTS = [` | Add a new line before `];` |
| Remove product | Product name | Delete the entire line |
| Change price | Product name | Change `price:12` to new number |
| Update FAQ | `<!-- ===== FAQ ===== -->` | Edit text in `faq-q` and `faq-a` |
| Update shipping | `<!-- ===== SHIPPING ===== -->` | Edit text inside `<p>` tags |
| Change Venmo | `@Stephie33` | Replace with new handle |
| Change Zelle | `gstephanie3@yahoo.com` | Replace with new email |
| Update Instagram | `pinthiz.la` | Replace with new handle |
| Raffle pricing | `const prices = {1: 5` | Change numbers (BOTH places!) |
| Raffle text | `Grand Slam Giveaway` | Edit title and description |

---

## NEED HELP?

If anything in this guide is confusing or you need changes made, reach out to Victoria. She built this site and can make changes quickly. But for simple things like adding products, changing prices, and updating text — you've got this! 💪

Remember: Always make a backup before making changes. The backup button is your best friend.

Welcome to running your own website, Steph! 💙💛⚾
