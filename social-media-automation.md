# Social Media Automation System

## Overview
Turn raw photos and rough context into polished, ready-to-post social media content.

## Current Flow (v1: WhatsApp + Peanut)

1. Client sends photo + rough text via WhatsApp
2. Forward to Peanut with "post for [client name]"
3. Peanut generates a polished post with:
   - Natural, human-sounding caption (no AI tells)
   - Relevant hashtags (5-10, mix of broad and local)
   - Emoji used sparingly and naturally
   - Platform-specific formatting
4. Peanut sends draft back for review
5. You approve and post manually (or Peanut posts via API)

## Post Generation Rules

### Tone
- Sound like a real person, not a brand
- Short sentences. No fluff.
- No em dashes. No "delve". No "it's worth noting".
- Write like someone who's proud of their work, not selling it

### Structure (Facebook)
- Line 1: Hook or statement about the work
- Line 2-3: Quick detail or story
- Last line: Soft CTA or location tag
- Hashtags at the end, not inline

### Example

**Input from client:**
> "finished kitchen frankston. white shaker doors, stone bench, customer happy"

**Generated post:**
> Another kitchen wrapped up in Frankston. White shaker doors, stone benchtops, soft close everything. The homeowner said it's the first time they've actually enjoyed cooking at home.
>
> Free measure and quote across Melbourne. Give us a call.
>
> #melbournekitchens #kitchenrenovation #cabinetmaker #frankston #customkitchen

## Hashtag Library (Cabinet Maker)

### Broad
#kitchendesign #kitchenrenovation #kitcheninspo #cabinetmaker #customcabinetry #homerenovation

### Local
#melbournekitchens #melbournerenovation #melbournebuilder #melbournehomes

### Suburb specific (rotate based on job location)
#frankston #brighton #stKilda #southyarra #richmond #doncaster #balwyn

## Future: API Auto-posting

### Facebook Graph API
- Create a Facebook App (developers.facebook.com)
- Get Page Access Token
- POST to /{page-id}/photos with message and image
- Needs: App Review for publish_pages permission

### Instagram Graph API
- Requires Facebook Business account linked to Instagram
- POST to /{ig-user-id}/media then /{ig-user-id}/media_publish
- Image must be publicly accessible URL

## Future: Multi-client Dashboard
- Each client has a content queue
- Weekly content calendar
- Auto-schedule posts for optimal times
- Performance tracking (likes, reach, engagement)
