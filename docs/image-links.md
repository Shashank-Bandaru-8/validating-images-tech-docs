# Image-wrapped links

Each section below is a different image or link case. Expected behavior is listed with the content.

## Empty image source, then more images

An image with an empty `src` comes first. The two images after it should still render.

<img src="" alt="Empty source — nothing to display" />

![AWS icon after the empty source. This image should render.](images/aws.svg)

![Azure icon after the empty source. This image should render.](images/azure.svg)

## Images wrapped in a valid link

Each image is inside a link with a normal `https://` URL. The image should render. Hovering should show that URL. Clicking should open the URL in a new tab, not zoom the image.

[![Cloud icon. Click should open https://example.com in a new tab.](images/cloud.svg)](https://example.com)

[![Data icon. Click should open https://www.youtube.com in a new tab.](images/data.svg)](https://www.youtube.com)

[![Billing icon. Click should open https://example.org in a new tab.](images/billing.svg)](https://example.org)

Text-only link (no image). Click should open the URL.

[Example site](https://example.com)

## Image wrapped in a broken link

The link URL cannot be parsed (`[` in the host). The image should still render. Clicking should not navigate.

<a href="http://www.my-internet.[top-level-domain]/pathname/[URLkey]"><img src="images/security.svg" alt="Security icon. Image should render. Click should not navigate." /></a>

Broken text-only link. This should show as plain text, not as a clickable link.

<a href="http://www.my-internet.[top-level-domain]/pathname/[URLkey]">this should become plain text</a>

## Images with no link

Relative images that are not wrapped in a link. Both should render.

![Architecture diagram. This image should render.](images/architecture.svg)

![OCI icon. This image should render.](images/oci.svg)
