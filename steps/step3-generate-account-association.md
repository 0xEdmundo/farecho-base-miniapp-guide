# Step 3 — Generate Account Association Using Base Build

Base Build verifies your domain by generating a signed set of values called `accountAssociation`.

### How to generate it:

1. Open Base Build → Account Association tool  
2. Enter your mini app URL:

   ```
   https://YOUR_DOMAIN
   ```

3. Click **Submit**  
4. Click **Generate Account Association**  
5. Sign the message with your wallet  
6. You will receive:

```json
"accountAssociation": {
  "header": "...",
  "payload": "...",
  "signature": "0x..."
}
```

### Insert these values into your manifest

Replace the empty fields in:

```json
"accountAssociation": {
  "header": "",
  "payload": "",
  "signature": ""
}
```

After updating the manifest, deploy your project.

Continue to Step 4 to validate your work.
