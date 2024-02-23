---
description: Dynamically embed content into your product.
---

# In-line Messages

In-line messages give you the ability to embed messages into your product. You can use inline messages to dynamically display banners, cards, or any content built with the Gist editor.

![](<.gitbook/assets/Inline Messages.png>)

Like overlay messages, inline messages can be triggered remotely via a [Broadcast](broadcasts.md), targeted to a customer via the [webhook](api/webhook.md), or manually integrated using the [Web](libraries/web.md), [Apple](https://gitlab.com/bourbonltd/gist-apple) & [Android](https://gitlab.com/bourbonltd/gist-android) libraries.

### How are messages embedded?

On web, the Gist library makes use of the [element id](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/id) within your web product, to find and replace the content of the element with the message. For native applications running on the Apple / Android platforms, a native View is returned from the Gist library. This leaves it up to the developer to decide where the view should sit within the product.

For more information on how to integrate inline messages you can look at the platform documentation below:

* [Web](libraries/web.md)
* [Apple](https://gitlab.com/bourbonltd/gist-apple)
* [Android](https://gitlab.com/bourbonltd/gist-android)
