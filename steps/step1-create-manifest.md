# Step 1 — Create the farcaster.json Manifest

Every Base-compatible mini app must include a manifest file located at:

```
/.well-known/farcaster.json
```

This file must be reachable publicly:

```
https://YOUR_DOMAIN/.well-known/farcaster.json
```

### ✅ Create the file in your project

Inside your project structure:

```
public/
  └── .well-known/
        └── farcaster.json
```

If the folders do not exist, create them manually.

### ✅ Purpose of this file

This manifest tells the Base App:

- who owns the mini app
- where its assets are hosted
- what metadata should be displayed
- which URLs to trust as the app’s domain

A starting template is provided in `/manifest-example/farcaster.json`.

Proceed to Step 2 to add your Base Build ownership.
