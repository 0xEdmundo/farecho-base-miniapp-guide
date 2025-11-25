# Step 2 — Add the Base Builder Ownership Section

Base App uses a special block inside the manifest to verify who owns the mini app.

Add the following inside `farcaster.json`:

```json
"baseBuilder": {
  "ownerAddress": "YOUR_WALLET_ADDRESS"
}
```

### Important:

- This must match the same wallet you use inside **Base Build**.
- If they do not match, Base App will reject your mini app.
- After editing the manifest, deploy your project so Base Build can read it.

Continue to Step 3 to generate your `accountAssociation`.
