# Image-wrapped links (IDP-10939)

Use this page in TechDocs with DevTools open (Elements + Network).
Each case says what 1.50 should have changed.

## 1. Empty src first (1.50 `addBaseUrl` continue)

If this still kills later images, the empty-src abort is not fixed.

<img src="" alt="empty-placeholder" />

Standalone after empty src:

![aws after empty](images/aws.svg)

![azure after empty](images/azure.svg)

## 2. Valid href wrapping image (Nationwide-shaped, 1.50 should already work)

Image should render. Click should open a new tab. `href` must stay on the `<a>`.

[![Valid example](images/cloud.svg)](https://example.com)

[![Valid youtube](images/data.svg)](https://www.youtube.com)

[![Nationwide-style SharePoint](images/billing.svg)](https://onyourside.sharepoint.com/sites/TechConsulting/Lists/Single%20Page%20App%20GP%20Videos/AllItems.aspx?referrer=OfficeHome%2EWeb&referrerScenario=StreamStartPage%2DRecommended&isDarkMode=false&viewid=e5a48e4b-39c2-4801-89b6-1005cdb92a96&playlistLayout=playback&itemId=2)

Text SharePoint link (control — no image):

[Enterprise Tech Consulting SharePoint](https://onyourside.sharepoint.com/sites/TechConsulting)

## 3. Unparseable href wrapping image (1.50 strip-href fallback)

Image should still show. Click should do nothing because `href` is removed.

<a href="http://www.my-internet.[top-level-domain]/pathname/[URLkey]"><img src="images/security.svg" alt="unparseable wrapped image" /></a>

Unparseable **text** link (still becomes plain text, no `<a>`):

<a href="http://www.my-internet.[top-level-domain]/pathname/[URLkey]">this should become plain text</a>

## 4. Relative standalone images (addBaseUrl rewrite)

![architecture](images/architecture.svg)
![oci](images/oci.svg)
