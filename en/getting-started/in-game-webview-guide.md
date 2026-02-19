metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/in-game-webview-guide
---

# Providing In-Game WebView

### When Providing the Market via In-Game WebView

If you plan to provide the Market via an in-game WebView, prior notification to LINE NEXT is required.

#### WebView Guidelines

* Add the `inapp=true` parameter when navigating to the Market
* Reference Example

```
<a href="https://{store domain}/auth?token={one time token}&inapp=true" target="_blank">Get Free Items</a>
```

* If the page opens in a new window within the web page, please open it in the external browser.
  * Opening a new window is not possible within the WebView.
  * Configure the web page to open new windows in the external browser.
    * Use `<a target="`_`blank">...</a>
` or `window.open(..., &quot;_blank&quot;)`
  * Reference document: [UniWebView - Supporting New Window](https://docs.uniwebview.com/guide/support-new-window.html)

{% hint style=&quot;warning&quot; %}
**Important Notes When Using Viewplex Webview**\
When using Viewplex Webview, the default behavior is to open all URLs within the current WebView.\
To proceed with payments, pages must open in a new window<mark style="color:red;">.</mark>
Therefore, <mark style="color:red;">implementation is required to detect the new window event and handle it separately.</mark>


To detect the new window event, you can use Viewplex&#x27;s [IWithPopups Interface](https://developer.vuplex.com/webview/IWithPopups).\
Utilize this interface to handle new window requests by opening the external browser.
{% endhint %}

* Recommended WebView Size
  * We recommend using the largest possible size, excluding areas that must remain visible in the game. This minimizes user inconvenience when checking product information or entering payment details.
  * The minimum guaranteed size requirements are as follows:
    * Width: 600px
    * Height: 375px 
