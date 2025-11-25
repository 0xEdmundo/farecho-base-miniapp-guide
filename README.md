# Base App Integration Guide  
_Step-by-step guide for integrating any Farcaster Mini App into the Base App_

This repository explains, in a beginner-friendly and fully reproducible way, how I integrated my Farcaster Mini App into the Base App.  
The example used in this guide is my own mini app:

- **Mini App URL:** https://swing-bark-290.app.ohara.ai  
- **Base Build Owner Wallet:** 0xd15b7af51bba85292f73255633b993c036ea2de3  

If you follow the steps in this repository, you can integrate your own Farcaster Mini App into the Base App the same way.

---

# 📍 What You Will Do in This Guide

1. Create the required `/.well-known/farcaster.json` manifest  
2. Add your Base Build wallet as the owner  
3. Generate the `accountAssociation` fields using Base Build  
4. Insert the generated fields into your manifest  
5. Validate everything inside Base Build Preview  
6. Publish your Mini App so that Base App can embed it

Everything is explained step by step with examples.

---

# ✅ Step 1 — Create the farcaster.json Manifest

Your mini app must expose a manifest at:

```
https://YOUR_DOMAIN/.well-known/farcaster.json
```

Inside your project, create the following folder and file:

```
public/.well-known/farcaster.json
```

This file tells Farcaster + Base information about:
- who owns the app
- what the app is called
- which URLs belong to the app
- what metadata should be shown inside Base App

A clean starting template is provided in  
`manifest-example/farcaster.json` inside this repo.

---

# ✅ Step 2 — Add Your Base Builder Wallet

Base App requires a section called `baseBuilder`:

```json
"baseBuilder": {
  "ownerAddress": "YOUR_WALLET_ADDRESS"
}
```

This wallet must match the wallet you use inside Base Build.

If they don’t match → Base App will not recognize your app.

---

# ✅ Step 3 — Generate Account Association in Base Build

Go to Base Build → Account Association tool and enter your App URL:

```
https://YOUR_DOMAIN
```

Base Build will ask you to sign a message with your wallet.  
After signing, it will return:

```json
"accountAssociation": {
  "header": "...",
  "payload": "...",
  "signature": "0x..."
}
```

Copy these values into your `farcaster.json`.

---

# ✅ Step 4 — Validate Using Base Build Preview

Use Base Build Preview to confirm:

- Manifest loads correctly  
- JSON is valid  
- `ownerAddress` matches your wallet  
- `accountAssociation` is valid  
- Metadata loads properly  

All green checks = Ready to use in Base App.

---

# ✅ Step 5 — Your Mini App is Now Fully Integrated

Once the manifest is valid, you can now embed your Mini App inside Base App by simply posting the URL:

```
https://YOUR_DOMAIN
```

Base App will automatically display your Mini App.

---

# 📦 Folder Structure in This Repo

```
/
├── README.md
├── manifest-example/
│   └── farcaster.json
└── steps/
    ├── step1-create-manifest.md
    ├── step2-add-basebuilder.md
    ├── step3-generate-account-association.md
    └── step4-validate-and-publish.md
```

Each file is beginner-friendly and contains a single task explained clearly.

---

# 🎉 Done

You now have a complete, public, beginner-friendly guide that shows how to integrate any Farcaster Mini App into the Base App — using your own example.
