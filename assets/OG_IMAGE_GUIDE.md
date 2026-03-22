# OG Image (Social Preview) Guide

The Open Graph image (`og-image.png`) is shown when someone shares your portfolio link on LinkedIn, Twitter/X, WhatsApp, Telegram, Slack, or any other platform that generates link previews.

## Specifications

- **Filename**: `og-image.png`
- **Dimensions**: 1200×628 pixels (standard OG image ratio)
- **Format**: PNG or JPEG (PNG preferred for crisp text)
- **Location**: Root of the project (same level as `index.html`)

## What to include

A good OG image typically contains:
- Your name (large, prominent)
- Your job title
- A visual element — your photo, a professional illustration, or abstract background
- Optional: your domain name or a subtle tagline

## Design tools

Free options:
- [Canva](https://canva.com) — search for "LinkedIn banner 1200x628" templates
- [Figma](https://figma.com) — create a frame at 1200×628px
- [Adobe Express](https://express.adobe.com) — free social image templates

## Where it appears

Once deployed, test your OG image with:
- [Open Graph Debugger (Facebook)](https://developers.facebook.com/tools/debug/)
- [Card Validator (Twitter/X)](https://cards-dev.twitter.com/validator)
- [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/)

## Updating

After replacing `og-image.png`, clear the cache in the social platform debuggers above so the new image propagates.
