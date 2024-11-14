# My infinite scrolling doesn't show all of my products.

## Background

In general, collections with infinite scrolling work like this:

1. The page loads with the first set of products, from page 1.
2. The user scrolls down to the end, your shop loads page 2 in the background, and then inserts the products from page 2 after all of the products already on the screen.
3. Repeat step 2, for each additional page available.
4. When the next page, loaded in the background, is found to have _no_ products on it, your shop stops trying to load additional pages.

With Locksmith, Step 4 is where things get interesting.

Product hiding is a frequently-used feature of Locksmith - it allows you to mix your protected and unprotected products in the same collection, ensuring that your customers see _only_ the products they _should_ see.

A side-effect of this is that each page of your collection _may not_ be "full". For example, if your page size is 10, a user that is authorized to see _everything_ will see 10 products on page 1, but a user who's only authorized to see 5 products _will only see 5 products_, even if page 2 has more products available.

(We have a whole article about this here:[ Improving collection filtering](../faq-i-see-blank-spaces-in-my-collections-and-or-searches-when-locking.md).)

Now, imagine that you have a collection for which the user can see 10 products on page 1, 10 products on page 2, _zero_ products on page 3, and another 10 products on page 4. This might be annoying _without_ infinite scrolling, but _with_ infinite scrolling it becomes impossible for the user to reach the last set of products. Remember: in step 4 of the infinite scrolling process, when an empty page is encountered, the shop stops trying to load more products.

## Solutions

1. Increase the page size (usually configurable in your theme settings), so that there are never any empty pages of products. It's much easier to accidentally have an empty page if each page is limited to a small number of products, and much harder to have that happen if you use the maximum page size of 50.
2. Or, hire a theme developer to alter the infinite scrolling code for your theme, so that it only stops trying to load more products after encountering _several_ empty pages, instead of after only encountering one.

## Notes

* This doesn't apply to server keys (e.g. passcodes, secret links). In most cases, infinite scrolling _will not_ work with these keys. If it doesn't work in your theme, there is no workaround, short of disabling infinite scrolling, or going with a new theme entirely.
