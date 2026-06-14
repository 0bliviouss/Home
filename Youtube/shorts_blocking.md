# Use this in your uBlock Origin ad blocker "My Filter" section:

```
! Hide Shorts shelf on the homepage
youtube.com##ytd-rich-section-renderer:has(#title-text:has-text(Shorts))

! Hide Shorts from the sidebar menu
youtube.com##ytd-guide-entry-renderer:has-text(Shorts)

! Hide Shorts from the subscriptions feed
youtube.com##ytd-grid-video-renderer:has(a[href^="/shorts/"])
```

_Credit: Standard_Web7962 on https://www.reddit.com/r/digitalminimalism/comments/1rvelz2/any_recommendations_for_youtube_shorts_blocker/_
