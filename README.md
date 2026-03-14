# shelby-xyz-cli
# shelby testnet/shelbynet zxcpmwallet

# Shelby CLI Setup Guide
### For GitHub Codespaces

---

## Step 1: Create a GitHub Repository

1. Go to **https://github.com/new**
2. Enter a repository name (e.g., `shelby-node`)
3. Select **Public** or **Private**
4. ✅ Check **"Add a README file"**
5. Click **Create repository**

---

## Step 2: Open Codespace

1. On your new repository page, click the green **Code** button
2. Select the **Codespaces** tab
3. Click **Create codespace on main**
4. Wait for the Codespace to load (takes ~1 minute)

---

## Step 3: Install Node.js + Shelby CLI

In the Codespace terminal, paste this command:

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt-get install -y nodejs && npm i -g @shelby-protocol/cli
```

Wait for installation to complete.

---

## Step 4: Get Your API Key

1. Open **https://geomi.dev**
2. Click **Sign Up** and create an account
3. On the overview page, click **"API Resource"**
4. Fill in:
   - **Network:** `Shelbynet`
   - **Resource Name:** `my-shelby`
   - **Usage Description:** `storage`
5. Click **Submit**
6. **Copy your API key** (starts with `aptoslabs_...`)

---

## Step 5: Initialize Shelby

Run:

```bash
shelby init
```

When prompted:

| Prompt | Action |
|--------|--------|
| API Key | Paste your API key from Step 4 |
| Private Key | Press **Enter** to generate new (or paste existing) |
| Other prompts | Press **Enter** to accept defaults |

---

## Step 6: Get Free Tokens

You need **APT** (gas fees) and **ShelbyUSD** (storage fees).

Run:

```bash
shelby faucet --no-open
```

This displays a faucet URL. Copy it and open in your browser.

On the faucet page:
1. Your address is pre-filled
2. Click **Fund** to get APT tokens
3. Click **Fund** again for ShelbyUSD tokens

---

## Step 7: Check Your Balance

```bash
shelby account balance
```

You should see both **APT** and **ShelbyUSD** with balances > 0.

---

## Step 8: Upload a File

Create a test file:

```bash
echo "Hello Shelby!" > test.txt
```

Upload it:

```bash
shelby upload test.txt myfile.txt -e "in 7 days" --assume-yes
```

---

## Step 9: Verify Upload

```bash
shelby account blobs
```

You should see `myfile.txt` in the list.

---

## Step 10: Download the File

```bash
shelby download myfile.txt downloaded.txt
```

Check it worked:

```bash
cat downloaded.txt
```

Output: `Hello Shelby!`

---

## ✅ Done!

You've successfully:
- Installed Shelby CLI
- Created an account with API key
- Uploaded and downloaded a file

---

## Quick Reference

| Command | Description |
|---------|-------------|
| `shelby account balance` | Check token balance |
| `shelby account blobs` | List uploaded files |
| `shelby upload [file] [name] -e [time]` | Upload a file |
| `shelby download [name] [save-as]` | Download a file |
| `shelby faucet` | Get free tokens |

---

**Need help?** Visit https://docs.shelby.xyz
