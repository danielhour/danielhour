# Exploring New APIs w/ Pixelfits

####

Whenever inspiration strikes for a new app, I blend the latest Apple APIs with technologies unexplored in my day job. This approach sharpens my skills, keeping me engaged with the evolving iOS landscape and its array of new tools. Here’s a closer look at the technologies I’ve woven into the fabric of Pixelfits, ordered by their significance to this project:

### Subject Lifting API

Introduced at WWDC 2023, this API is the lifeblood of Pixelfits. The whole idea of magically ripping the subject out of its background and placing it onto a mannequin is how we got here in the first place.

- [WWDC23: Lift subjects from images in your app](https://developer.apple.com/videos/play/wwdc2023/10176/)
- [WWDC23 Notes](https://www.wwdcnotes.com/notes/wwdc23/10176/)

### Share Extension

A familiar tool in the Apple ecosystem but new to my arsenal, the Share Extension has been just as integral as the Subject Lifting API. It allows seamless content sharing from mobile browsers to the app, elevating the overall user experience.

- [Share Extension Overview](https://developer.apple.com/library/archive/documentation/General/Conceptual/ExtensibilityPG/Share.html)

### SwiftData

I wanted data to be saved locally but Core Data is the absolute WORST. You know it. I know it. Apple knows it. And that is probably why they introduced SwiftData at WWDC23. Yes, I know it’s technically just a layer on top of Core Data but it’s abstracted away a lot of the boilerplate nonsense you needed to configure just to get up and running. And added benefit was that to get it to sync to Cloudkit, all I had to do was tap a checkbox! So saved locally & to the cloud without building out an entire backend!

- [WWDC23: Model your schema with SwiftData](https://developer.apple.com/videos/play/wwdc2023/10195/)
- [SwiftData and iCloud Sync](https://www.hackingwithswift.com/quick-start/swiftdata/how-to-sync-swiftdata-with-icloud)
- [SwiftData is incredible Reddit Thread](https://www.reddit.com/r/SwiftUI/comments/145yilw/swiftdata_is_incredible/)

### StoreKit 2

Well we've done all this work now so we might as well try to make some money huh? So that meant adding in some In-App Purchases. But I hadn't messed with IAPs in 8 years! Storekit 2 definitely makes it easier to get up & running.

- [WWDC23: Meet StoreKit for SwiftUI](https://developer.apple.com/videos/play/wwdc2023/10013/)
- [StoreKit Testing in Xcode](https://developer.apple.com/documentation/xcode/setting-up-storekit-testing-in-xcode/)

### Apple Search Ads

I believe you get $100 in free credits if you set up under “Basic”. Use them!

- [Apple Search Ads](https://searchads.apple.com/)
- [How to get Promo Credits](https://searchads.apple.com/help/billing/0032-apple-search-ads-promo-credit)

### String Catalog

This one directly correlates to Search Ads since I realized I could promote Pixelfits across the globe vs just the country. But I very much did not want to localize the app unless Apple had made it easier than my days at GOAT where it was just a file of loosely typed strings. String Catalogs (announced at WWDC23) simplifies ALL of that.

- [WWDC23: Discover String Catalogs](https://developer.apple.com/videos/play/wwdc2023/10155)

### [TelemetryDeck](https://telemetrydeck.com/) & [Embrace.io](https://embrace.io/)

In the spirit of exploration, I decided to not automatically reach for Firebase/Crashlytics and to give TelemetryDeck & Embrace a try. Granted, it does split one thing (Crashlytics) into two (analytics & crash reporting respectively), I have been pleased with how simple both were to set up and how lightweight they are in my app. TelemetryDeck's approach to analytics also aligns with current privacy trends.

- [TelemtryDeck Setup Guide](https://telemetrydeck.com/docs/guides/swift-setup/)
- [Embrace vs Crashlytics](https://embrace.io/crashlytics-alternative/)

### Wrapping Up

And there we have it – a quick tour through the technological landscape that shaped Pixelfits. This post provides a glimpse into the tools and APIs that brought Pixelfits to life. Looking ahead, I plan to delve into specific aspects in more detail, unraveling both the challenges and the successes encountered along the way.

In the meantime, I'd love to hear from you. Are there any specific aspects of Pixelfits' development that pique your interest? Any tech headaches you've encountered in your projects that you're wondering if I faced too? Drop your thoughts and questions [@dhour](https://www.instagram.com/dhour) or [@pixelfits.app](https://www.instagram.com/pixelfits.app)!
