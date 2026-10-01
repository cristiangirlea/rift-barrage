# Deploying the website

`site/` is a plain static site (no build step). It is served by Cloudflare Pages at `riftbarrage.cristiangirlea.ro`, because the `cristiangirlea.ro` zone is already on Cloudflare.

## One-time setup (Cloudflare dashboard)

1. **Workers & Pages → Create → Pages → Connect to Git**, then choose `cristiangirlea/rift-barrage`.
2. Configure the build:
   - Framework preset: **None**
   - Build command: *(empty)*
   - Build output directory: **`site`**
3. **Save and Deploy.** Every push to `main` redeploys.
4. Open the project's **Custom domains → Set up a custom domain** and enter `riftbarrage.cristiangirlea.ro`. Cloudflare creates the DNS record itself, because the zone is in the same account, and issues the HTTPS certificate.

## Releases

Builds are attached to GitHub Releases with stable file names, so the site's links (`releases/latest/download/…`) always point at the newest preview:

- `RiftBarrage-android.apk`
- `RiftBarrage-windows-x64.zip`
- `SHA256SUMS.txt`
