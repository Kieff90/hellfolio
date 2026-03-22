# IndexNow Setup Guide

IndexNow is a protocol that lets search engines (Bing, Yandex, and others) know immediately when your content changes. This means faster indexing after you deploy updates.

## Step 1: Get your IndexNow key

1. Go to [Bing Webmaster Tools](https://www.bing.com/webmasters)
2. Sign in and add your website
3. Navigate to **Settings → IndexNow**
4. Bing will generate a unique key for you (looks like: `a1b2c3d4e5f6...`)

## Step 2: Add the key file to your site

Rename `YOUR_INDEXNOW_KEY.txt` to match your actual key:

```
mv YOUR_INDEXNOW_KEY.txt a1b2c3d4e5f6.txt
```

The file must be accessible at:
```
https://yourdomain.com/a1b2c3d4e5f6.txt
```

Its content must be exactly the key value (no extra whitespace):
```
a1b2c3d4e5f6
```

## Step 3: Configure GitHub Secrets

In your GitHub repository, go to **Settings → Secrets and variables → Actions**, and add:

| Secret name     | Value                              |
|----------------|------------------------------------|
| `INDEXNOW_KEY` | Your IndexNow key (e.g. `a1b2c3d4`) |
| `SITE_URL`     | Your site URL (e.g. `https://yourdomain.com`) |

The GitHub Actions workflow (`.github/workflows/deploy.yml`) will automatically notify IndexNow after every deploy.

## How it works

After each successful deploy, the workflow calls:
```
https://api.indexnow.org/indexnow?url=https://yourdomain.com/&key=YOUR_KEY
```

This tells Bing (and partner engines) to immediately crawl and re-index your page.

## Verification

You can verify your setup at:
- [Bing Webmaster Tools → IndexNow](https://www.bing.com/webmasters) — check submission history
- Direct API test: `curl "https://api.indexnow.org/indexnow?url=https://yourdomain.com/&key=YOUR_KEY"`
  - A `200` response means success
  - A `202` means accepted for processing
