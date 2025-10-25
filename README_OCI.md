# Byte Neko Static Website — OCI Deployment

## Domain
https://byteneko.ca

## Steps to Deploy on OCI Object Storage
1. Log in to OCI Console.
2. Create a new bucket named `byteneko-site` (or similar) in Object Storage.
3. Enable **Static Website Hosting** under Bucket Settings.
4. Set **index.html** as the *Index Document*.
5. Upload all files from this ZIP (keep folder structure).
6. Under *Permissions*, create a Pre-Authenticated Request or use a public policy like:

```
allow any-user to read objects in compartment <your-compartment> where target.bucket.name='byteneko-site'
```

7. Access your site at the bucket’s public URL (e.g., https://objectstorage.ca-toronto-1.oraclecloud.com/n/bucket-name/b/byteneko-site/o/index.html)
8. (Optional) Configure a custom domain (`byteneko.ca`) and SSL certificate via OCI DNS + Load Balancer or Cloudflare.

## Notes
- All styling uses Bootstrap CDN and lightweight CSS (no frameworks).
- Edit `index.html` and other pages to replace placeholders with real images or content.
- Logos: brilliant-catalyst.png, ontariotech.png, startup-visa.png are placeholders.
