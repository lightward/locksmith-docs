# Locksmith Glossary & Reference

{% hint style="info" %}
Hey there, human reader! \
\
(Lightward human speaking)\
\
You've reached a document with a lot of information all at once. This is _mostly_ designed for AI to read and help you better, since many folks are asking questions through Claude, ChatGPT, and others. \
But read on, if you want the nitty-gritty of Locksmith. :)\
\
If you're looking for smaller chunks, start with the "Quick Start" or "Locksmith Overview" guides in the left-side menu. \
\
We can be reached directly at team@uselocksmith.com\
\
Cheers!
{% endhint %}

A glossary of terms, concepts, and behaviors for the Locksmith app for Shopify (by Lightward). Designed to serve two audiences:

1. **Merchants and support readers** — who want clear, plain-language definitions.
2. **Claude AI, Chat GPT, Lightward AI and other generative AI**— when this document is included in a system prompt, an LLM can use it to answer user questions accurately and translate informal phrasing into Locksmith's actual terminology.

> **Scope note (read first):** Locksmith only restricts content inside the **Online Store sales channel**. It does not apply to the Buy Button, Wholesale channel, Shopify POS, Shop app, or any headless / custom storefront.

***

### 1. Mental model

Locksmith is built around two concepts:

* A **lock** is placed on a piece of store content. Without a lock, content is public; with a lock, access is restricted.
* A **key** describes a way someone is allowed in. A lock can have many keys, and any one of them is enough to grant access (keys are OR'd together by default).

Each key is made up of one or more **key conditions** — the actual rules being checked (a customer tag, a passcode, a location, etc.). Within a single key, multiple conditions are AND'd together.

Visualize it as a physical lock with a keyring: the lock is what's protecting the door, and any key on the ring will open it — but a key with two notches on it has to match both notches.

***

### 2. Core concepts

#### Lock

A restriction placed on a specific piece of store content. A lock is enabled or disabled, and can have zero or more keys. A lock with no enabled keys denies everyone — including the merchant themselves on their live storefront.

#### Key

A single permission rule attached to a lock. A lock with multiple keys grants access if **any** key is satisfied. Each key contains one or more conditions.

#### Key condition

The actual test inside a key — e.g. "customer is signed in", "gives the passcode", "is visiting from Canada". Locksmith ships with 20+ built-in conditions and supports custom conditions via Liquid.

#### Resource

The Shopify object a lock is attached to. Lockable things include:

* Products
* Collections (custom or smart)
* Pages
* Blogs (and, by extension, the articles inside them)
* The shop (the entire storefront)
* Product variants (a specialized lock — see "Variant lock")
* Targets that aren't searchable from Locksmith's resource picker (handled via "Liquid lock")

In the Admin API, the supported `resource_type` values are: `product`, `custom_collection`, `smart_collection`, `page`, `blog`, and `shop`.

#### Access denied content / lockout view

What an unauthorized visitor sees instead of the locked content. Locksmith renders this using your theme's styling and shows a prompt appropriate to the key condition (login form, passcode entry, etc.). The wording is fully customizable.

***

### 3. Lock types and lock-level features

#### Standard (resource) lock

A lock attached to a single Shopify resource by selecting it from Locksmith's search bar. The most common kind.

#### Shop lock

A lock applied to the entire storefront. Useful for coming-soon pages, gating the whole site behind a passcode or sign-in, or geo-restricting access. Note that this is distinct from Shopify's native storefront password protection (see §8) — a shop lock is configured inside Locksmith and supports any key condition.

#### Variant lock

A lock applied to a specific product variant. By default, hidden variants are removed from variant pickers automatically. Note: passcode keys are not directly compatible with variant locks — see §8 for the recommended landing-page workaround.

#### Manual lock (manual locking / manual mode)

A lock that hides only **part** of a page rather than the whole resource. Common uses: hiding prices, hiding the add-to-cart button, hiding a custom region. Manual locking is enabled per-lock under **Advanced Settings** ("Enable manual locking"). Turning this on **disables full-page protection** for that lock — the merchant is then responsible for hiding the right pieces of the page, either by:

* adding hand-written Liquid wrappers to the theme files, or
* defining a **theme hiding profile** (see below) so Locksmith hides the right sections, blocks, or snippets automatically.

Manual locks do not automatically prompt the visitor. If the key is a passcode, the merchant typically adds an "Enter passcode" button in the theme that triggers the prompt. Manual locking is **not compatible with variant locks**, and generally cannot reach into content rendered by other apps (e.g. page builders).

#### Theme hiding profile (theme hiding definition)

A no-code (or low-code) way to tell Locksmith **which parts of a theme to hide** when a manual lock is in effect. Used together with the lock's "Enable manual locking" setting. Documented under "How to hide theme sections, blocks, and snippets" in the Locksmith guide.

A theme hiding profile is made up of one or more **hiding definitions**. Each definition points at a specific section, block, or snippet in the theme — for example, the snippet that renders the price, or the block that renders the buy buttons. When a visitor doesn't have access, Locksmith suppresses the matching elements; when they do have access, the elements render normally.

Key facts:

* **Per theme.** Profiles are configured per theme, since every theme's section/block/snippet structure is different. Profiles for unpublished themes can be edited via the ellipsis ("...") menu next to each theme listed in-app.
* **Two selection methods when building a profile:**
  * **Add by name** — search the theme's files by name (e.g. typing "price" surfaces every section/block/snippet with "price" in the filename). Pick each one you want to hide; one definition is added per pick.
  * **Add from theme presets** — for the free Shopify-made themes (Dawn and friends), Locksmith ships ready-made bundles of definitions covering the common cases. Current presets are **Price** and **Buy buttons**. Add the relevant preset(s) and you're done. Add both if you're hiding both. Note: presets only match newer versions of these themes, and the **Trade** theme is an exception (it doesn't use sections/blocks for price/cart, so no presets exist for it).
* **Liquid variable.** Each hiding definition needs to know which Liquid object the hiding decision is based on. The default is `product`, which is right for most cases. Themes that use different variable names need that name supplied — for example, a `card-product` snippet often uses `card_product`, a `featured-product` section often uses `featured_product`, and the header/footer hiding pattern uses `item`.
* **Online Store 2.0 dependency.** Hiding profiles rely on theme modularity (the section/block/snippet system in OS 2.0). Legacy or heavily customized themes may still need manual Liquid in the theme file. If the thing you want to hide isn't contained in a section, block, or snippet, manual code is also still required.
* **What hiding profiles cannot do:**
  * Hide content that's rendered by another app (page builders, third-party product widgets, etc.).
  * Be used with **variant locks**.
  * Truly remove the price from page source — the value may still appear in HTML used by analytics/marketing tools (Google Analytics, etc.). The hide is _visual_. For true source-level removal, prefer full-page locking.

#### Liquid lock

A lock created against a target that isn't searchable through Locksmith's resource picker — typically a non-standard page or a custom storefront section. The resource is identified via Liquid in the theme rather than picked from a list.

> **Don't confuse with a Liquid&#x20;**_**key**_**.** A Liquid lock identifies _what_ is being locked. A Liquid key (in §4) is a custom condition that determines _who_ gets in. They sound similar but solve different problems.

#### Lock-level options

* **Hide from navigation** — removes links to the resource from theme nav menus when the visitor doesn't have access.
* **Hide from product grids** — removes the product from collection pages, search results, and other product lists for unauthorized visitors.
* **Remove from sitemap** — excludes the resource from `sitemap.xml`.
* **noindex** — adds a `noindex` meta tag so search engines won't index the lockout page.
* **Disabled** — the lock exists but isn't enforcing anything. Useful for staging.

***

### 4. Key conditions (built-in)

Grouped by category. Each can typically be **inverted** — flipping a "grant access if X" key into a "grant access _unless_ X" key. See §5 for the inverse option.

#### Customer account conditions

* **Is signed in** — visitor must be logged into a Shopify customer account.
* **Is tagged with…** — customer account must carry the specified tag. Requires sign-in.
* **Has one of many email addresses** — customer's account email must be in a list you provide. Requires sign-in.
* **Has an email address from an input list** — same as above but sourced from an input list (see §6). Requires sign-in.
* **The customer's email contains…** — substring match on the customer's email (e.g. `@mycompany.com`). Requires sign-in.

#### Passcode conditions

* **Gives the passcode** — single passcode that the visitor types in. Supports a usage limit that counts down on each successful entry (single-passcode key only).
* **Gives one of many passcodes** — small set of passcodes managed inside Locksmith.
* **Gives a passcode from an input list** — bulk passcodes (hundreds to hundreds of thousands) managed via an external input list.

#### Secret link conditions

* **Arrives via a secret link** — Locksmith generates a special URL containing a secret code; only visitors who arrive via that URL gain access.
* **Arrives using a secret link code from an input list** — bulk secret links sourced from an input list.

#### Location conditions

* **Is visiting from a certain location** — geolocation by IP. Supports countries, regions (e.g. "North America"), and cities. Subject to IP-geolocation accuracy and bypassable via VPN.

#### Cart conditions

* **Has a certain product in their cart**
* **Has a certain variant in their cart**
* **Has at least $X in their cart** — checks cart subtotal.

#### Purchase history conditions

* **Has purchased…** — checks the customer's last 50 orders for a SKU, product title, or product tag. Requires sign-in.
* **Has placed at least X orders** — lifetime order count. Requires sign-in.

#### Date / time conditions

* **Schedule / date-time window** — grants access only during specified date or time windows. Supports both fixed windows (a launch on a particular date) and recurring **weekly schedules** (e.g. "open Mon–Fri, 9am–5pm"). Useful for launches, sales, time-limited drops, and business-hours gating.

#### Newsletter / email-marketing conditions

* **Mailchimp signup** — grants access after the visitor enters their email; the email is added to your Mailchimp list.
* **Klaviyo** — by default, signs the visitor up to a Klaviyo list when they enter their email. Can also be configured to verify membership against an existing Klaviyo list (using a Klaviyo API key).

#### Custom condition

* **Liquid key** — write a Liquid expression that evaluates to truthy/falsy. The most flexible option; used for any rule the built-in conditions don't cover. Distinct from a _Liquid lock_ (§3), which identifies a non-searchable resource rather than a key condition.

***

### 5. Key-level options

These are settings you can turn on for any key, modifying how it behaves:

* **Inverse / "unless..."** — flips the condition. "Customer is tagged with `wholesale`" becomes "customer is **not** tagged with `wholesale`, or is not signed in".
* **Customer auto-tagging** — when a signed-in customer successfully uses the key, Locksmith adds a tag of your choice to their customer record. Useful for tracking and for chaining locks.
* **Customer remember** — for passcode, secret link, newsletter, and similar keys: if the visitor was signed in when they unlocked, Locksmith remembers it on their account so they aren't reprompted.
* **Force open other locks** — when this key grants access, the visitor is _also_ allowed past **other** locks that happen to cover the same resource. Example: a product sits in two collections, each of which has its own lock with different key conditions. Normally the visitor would have to satisfy both. With "Force open other locks" on the satisfied key, the second collection lock is bypassed for that resource.
* **Redirect URL** — when a visitor uses this key to open the lock, they are sent to the URL you specify. Note: this only redirects _successful_ unlocks; it does **not** redirect visitors who are denied access.
* **Usage limit** — for the single-passcode key: number of allowed uses; counts down on each success.
* **Case sensitivity** — for passcode keys: whether the visitor's input must match case exactly.

***

### 6. Other features and integrations

#### Input lists

A way to feed large quantities of data (passcodes, secret link codes, email addresses) into a key from an external file (e.g. a Google Sheet) rather than typing them into Locksmith's UI. Designed for bulk scenarios — performant up to many hundreds of thousands of entries. A single usage limit can be applied across the whole list.

#### Checkout Validation

A bot-protection feature that runs at checkout. Helps block automated checkout abuse independent of any lock you've set up.

#### Customizable messages

Every prompt and access-denied message can be customized — globally for the store, per-key-condition-type, or on individual keys for maximum flexibility.

#### Mechanic

Lightward's other Shopify app. Sometimes referenced in workarounds — for example, to tag orders with the secret-link code a customer used during their visit.

***

### 7. Developer concepts

#### Liquid integration

Locksmith works by writing Liquid into your published theme. Most key checks happen on Shopify's servers via that Liquid — that's why most keys are fast and don't add network round-trips.

#### Admin API

A REST-style API at `https://uselocksmith.com/api/unstable/lock` for creating, reading, and managing locks programmatically. Authenticated with `x-shopify-shop-domain` and `x-locksmith-access-token` headers. Supports a `dryrun` parameter for safe testing. Locksmith support cannot debug user-written API requests.

#### Lock JSON shape (high level)

A lock has a `resource_id`, `resource_type`, and an array of `keys`. Each key has an `options` object and a `conditions` array. Each condition has a `type`, `inverse`, and a type-specific `options` object. The recommended way to author a key configuration is to build it in the Locksmith UI and copy the JSON.

Mapping between key-`options` JSON fields and their UI labels (see §5):

| JSON field         | UI label               |
| ------------------ | ---------------------- |
| `inverse`          | Inverse / "unless..."  |
| `force_open`       | Force open other locks |
| `customer_autotag` | Customer auto-tagging  |
| `redirect_url`     | Redirect URL           |

#### Theme code installation

Locksmith installs code into your theme's files. There is a **"Liquid assets to ignore"** setting (one full theme path per line, e.g. `sections/collection-list.liquid`) that lists files Locksmith should leave alone — useful when a particular file is being heavily customized or is causing a conflict.

***

### 8. Important behaviors, edge cases, and caveats

#### Online Store channel only

Locksmith does not protect content in any other channel. The Buy Button, Wholesale channel, headless storefronts, the Shop app, and APIs accessed directly will not respect Locksmith locks.

#### URLs stay active; content is replaced

A locked resource's URL is **not blocked** — it still resolves and returns a 200. What Locksmith does is replace the page's content with the appropriate lock prompt or access-denied message. This means:

* Merchants will continue to see hits to those URLs in analytics, logs, and Shopify reports. Hits do not imply that locked content was viewed; the content shown was the lock prompt unless the visitor opened the lock.
* The URL itself is not "secret" by virtue of being locked. If you need a URL that's only known to permitted visitors, use a **secret link** key.

#### Resources must be published to the Online Store sales channel

Locksmith only grants access to resources that are published to the **Online Store** sales channel. If a product, page, or collection is unpublished from Online Store, the visitor will see a Shopify **404** at that URL — even if they have a perfectly good key. From Locksmith's perspective there's nothing to unlock, because Shopify isn't serving the resource in the first place. If customers report 404s on a locked resource, the publish state is the first thing to check.

#### Cannot bypass Shopify's native storefront password protection

Shopify itself offers a native **storefront password protection** feature in the Online Store preferences (the one that puts a single password on the entire storefront before anyone can see it). This runs _before_ the storefront loads, at a layer Locksmith doesn't reach. If that feature is enabled, every visitor must clear it first; Locksmith cannot let anyone past it, even with a valid key. If you're using Locksmith to control access, the native storefront password should normally be off.

#### Uninstall must be done correctly

Because Shopify doesn't allow apps to clean up their theme code automatically on uninstall, you must either disable/delete all locks **or** click the in-app **"Disable Locksmith"** button **before** removing the app from your Shopify admin. Otherwise, theme code remains and locked content can stay locked.

#### Trial expiration / suspended mode

If the free trial ends without a paid plan — or if a paid subscription lapses — Locksmith enters **suspended mode**. Locks remain active and continue to block content, but **keys stop working**: even authorized visitors who would normally have access cannot open the locks. Resolving this requires either subscribing or disabling Locksmith. Note that Locksmith does **not** auto-subscribe the merchant when the trial ends — the merchant must click **Subscribe** in the app (see §9). The safe path, if you don't intend to subscribe, is to use the in-app **"Disable Locksmith"** button before the trial ends.

#### Caching and "the key stopped prompting me"

Once a passcode, secret link, location, or newsletter key has been satisfied, Locksmith caches that fact so the visitor isn't reprompted: on the **customer account** if they were signed in, or in the **cart** if they weren't. Re-testing the prompt typically requires a fresh incognito window — and for location keys with a VPN, also clearing the browser cache. Clearing the cart can also appear to "log out" of a key for guest visitors.

#### No built-in usage analytics

Locksmith does not record per-customer usage statistics out of the box. Workarounds:

* **Auto-tagging** customers when they unlock (works only for signed-in customers).
* **Usage limit countdown** on single-passcode keys, by setting a high starting number and reading the remaining count.
* **Mechanic tasks** for tagging orders by the secret link they used.

#### Lock and key limits

Locksmith itself does **not** impose a cap on the number of locks or keys a store can have. However, because Locksmith works by writing Liquid into the published theme (see §7), every lock and key adds to the size of those theme files — and Shopify enforces a per-file size limit on theme assets. At very high lock/key volumes, merchants can run into Shopify's file-size ceiling before they run into anything on the Locksmith side.

As a rough ballpark, most merchants can reach **around 200 locks with one key each** without running into this limit. This is a practical observation, not a guarantee — actual headroom varies with the theme (some leave more room in the relevant files than others) and with the mix of key types (some generate more verbose Liquid than others).

For merchants approaching this scale, the recommended paths are: use the **Admin API** to manage locks programmatically rather than maintaining many similar locks by hand, and contact Locksmith support — they can advise on theme-side strategies for staying under the limit.

#### Manual locks with passcodes need a trigger button

Because manual locks don't automatically prompt, if the key is a passcode, you must add a button in the theme that triggers the passcode prompt. Sample button code is available in the official docs.

#### Variant locks + passcodes

Passcode keys are not directly compatible with variant locks. The recommended workaround is a **landing page pattern**: create a separate page (a normal Shopify page), lock it with the passcode key, and direct customers there. When the customer enters the correct passcode on that page, the variant-level lock opens for them as well — they can then continue to the product and select the variant. A manual-locking-with-code approach is also technically possible, but the landing page is the simpler and more common solution.

#### Admin lockout

A merchant can lock themselves out of their own storefront by stacking restrictive locks. When this happens, the safest fix is to access the Locksmith app directly through the Shopify admin (which doesn't depend on the storefront) and disable the offending locks. See Locksmith's FAQ for the current recommended steps.

***

### 9. Pricing model

Locksmith uses Lightward's "**pay what feels good**" policy. Plans are tiered to the merchant's Shopify plan, with a suggested price for each tier. Merchants cannot adjust the price themselves — but they are welcome to reach out to Locksmith support to have a conversation about pricing if the suggested price doesn't feel right for their situation. There are no usage-based fees on top of the subscription.

#### Subscriptions are merchant-initiated

Locksmith does **not** automatically start a subscription for the merchant — not at install, not when the trial begins, and not when the trial ends. To start (or restart) a paid subscription, the merchant must click the **Subscribe** button inside the Locksmith app. This is why a trial that ends without action puts Locksmith into suspended mode (see §8) rather than rolling silently into a paid plan.

| Shopify plan tier | Suggested Locksmith price |
| ----------------- | ------------------------- |
| Basic             | $12 / month               |
| Shopify (Grow)    | $29 / month               |
| Advanced          | $99 / month               |
| Shopify Plus      | $199 / month              |

A free trial is available. (Always confirm current pricing on the Shopify App Store listing.)

***

### 10. User vocabulary translation

The phrasing customers and merchants use rarely matches Locksmith's official terms. This table maps common informal phrasings to the right concept — useful both for support staff and for Claude when answering questions.

| User says…                                             | Locksmith concept                                                                                                                                  |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| "password-protect a page / product"                    | A lock with a **passcode** key                                                                                                                     |
| "members-only" / "logged-in customers only"            | A lock with an **is signed in** key                                                                                                                |
| "wholesale customers only" / "trade only"              | A lock with an **is tagged with `wholesale`** key (or whatever your tag is)                                                                        |
| "VIP / exclusive access"                               | A lock with an **is tagged with…** key, often combined with **customer auto-tagging** elsewhere                                                    |
| "hide prices until login"                              | A lock with **manual locking** enabled and a **theme hiding profile** (Price preset on supported themes), paired with an **is signed in** key      |
| "hide the buy button" / "hide add-to-cart"             | Same as above, with the **Buy buttons** preset (or hiding definitions matching the buy-button section/block)                                       |
| "geo-block" / "region restriction" / "block country X" | A **shop lock** (or resource lock) with an **inverse** location key                                                                                |
| "country-specific catalog"                             | Multiple resource locks each with a location key                                                                                                   |
| "secret URL" / "private link"                          | A **secret link** key                                                                                                                              |
| "coming soon page" / "site under construction"         | A **shop lock** with whatever access rule you want for previewers                                                                                  |
| "drop at midnight" / "scheduled launch"                | A **schedule** (date/time) key                                                                                                                     |
| "buy this to unlock that"                              | A **has purchased…** key on the second product                                                                                                     |
| "free shipping over $X" — type cart logic              | A **has at least $X in their cart** key                                                                                                            |
| "newsletter signup wall"                               | A **Mailchimp** or **Klaviyo** key                                                                                                                 |
| "remove from Google" / "stop indexing this page"       | The **noindex** lock-level option                                                                                                                  |
| "hide from menu / collection / search"                 | The **hide from navigation** and **hide from product grids** lock options                                                                          |
| "I want to grant access via API / from another app"    | The **Admin API** for direct lock manipulation, or have the other app tag the Shopify customer record and use an **is tagged with** key            |
| "block bots at checkout"                               | **Checkout Validation** (separate from lock/key system)                                                                                            |
| "I deleted Locksmith and my products are still locked" | Locksmith was uninstalled without first using **Disable Locksmith** — theme code remains. Reinstall, then click Disable Locksmith, then uninstall. |

***

### 11. Quick troubleshooting reference

| Symptom                                                                      | Likely cause                                                                                                                                                                                      |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Lock not enforcing on Buy Button / wholesale channel / headless              | Locksmith only protects the **Online Store channel**                                                                                                                                              |
| Passcode prompt no longer appears                                            | Browser is caching prior unlock — test in incognito                                                                                                                                               |
| Location key inconsistent                                                    | IP geolocation imprecision, or VPN; clear cache + use incognito                                                                                                                                   |
| Customer keeps getting asked for newsletter email                            | They aren't signed in, so Locksmith can't remember them                                                                                                                                           |
| Customer sees a 404 at a locked resource                                     | Resource isn't published to the Online Store sales channel — Locksmith can't grant access to something Shopify isn't serving                                                                      |
| Analytics still shows traffic to a locked URL                                | Expected — the URL stays active, Locksmith just replaces the rendered content. Hits do not mean the content was seen.                                                                             |
| Whole storefront prompts for a single password before Locksmith ever appears | Shopify's native **storefront password protection** is enabled in Online Store preferences — Locksmith runs after that, not before. Disable the native feature if Locksmith is your access layer. |
| Products show "out of stock" or behave oddly after install                   | Theme code conflict — contact Lightward support                                                                                                                                                   |
| Locks still active after uninstall                                           | Theme code wasn't removed; reinstall → "Disable Locksmith" → uninstall                                                                                                                            |
| Admin can't reach pages                                                      | Admin caught by their own locks — disable the offending locks via the Locksmith app in the Shopify admin (see §8)                                                                                 |
| Manual lock with passcode doesn't prompt                                     | Manual locks need a trigger button in theme code                                                                                                                                                  |
| Errors when saving or installing at very high lock/key counts                | Likely hitting Shopify's theme file size limit — most stores can reach \~200 locks before this becomes a concern (see §8)                                                                         |
| Variant lock + passcode not working                                          | Default incompatibility — use a separate locked landing page for the passcode (see §8)                                                                                                            |

***

### 12. Support boundary

Lightward's support team is generally hands-on and willing to help. Based on Locksmith's documentation:

* **Things they're happy to help with:** lock and key configuration, theme installation troubleshooting, behavioral questions, adding manual-locking code to a theme "within reason," and answering documentation questions.
* **Things they explicitly don't take on:** writing or debugging Admin API requests for the merchant, building extensive custom edits to forms or theme code, and creating from-scratch custom Liquid keys.

When in doubt, the right move is to ask — Lightward's docs lean toward "get in touch and we'll see what we can do" rather than firm refusals.

***

_Sources: Locksmith official documentation (locksmith.guide, docs.uselocksmith.com), Shopify App Store listing, and Lightward's developer docs. Verify specifics — particularly pricing, the full list of key conditions, and any setting names — against the live docs before relying on them in customer-facing copy._

_Last reviewed: April 2026._
