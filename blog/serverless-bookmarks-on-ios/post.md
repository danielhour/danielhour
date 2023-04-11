# Serverless Bookmarks On iOS

####

Bookmarks & Favoriting - an essential tool for both shoppers and retailers in the world of e-commerce. But what if there isn't enough time to spin up an entire backend service for it? Is there a way to do it that doesn't just save it locally to the device (i.e. NSUserDefaults - more on that later)?

Well we recently solved that at Hodinkee by utiilizing iOS's NSUbiquitousKeyValueStore.

NSUbiquitousKeyValueStore is a great solution that allows you to store small amounts of data in iCloud and synchronize them across devices without the need for a server. NSUbiquitousKeyValueStore is a key-value store provided by Apple that automatically synchronizes data across all of a user's devices using iCloud. In this post, I'll show you how to use NSUbiquitousKeyValueStore to store bookmarks in iCloud.

Here are the steps to store bookmarks using NSUbiquitousKeyValueStore:

1. Enable iCloud on your devices.

   To use NSUbiquitousKeyValueStore, you need to have iCloud enabled on all of your devices. Make sure you're signed in to the same iCloud account on all of your devices. (It _is_ technically a limitation but since all apps downloaded from The App Store require an AppleID, this shouldn't really be an issue.)

2. Create a reference to NSUbiquitousKeyValueStore.

   In your app, create a reference to NSUbiquitousKeyValueStore using the following code:

   ```
   let store = NSUbiquitousKeyValueStore.default
   ```

3. Save bookmarks.

   In the below code, `bookmarkData` is the bookmark data you want to store (e.g., a URL), and `bookmarkName` is a unique name for the bookmark.

   ```
   store.set(bookmarkData, forKey: bookmarkName)
   store.synchronize()
   ```

4. Load bookmarks.

   In the below code, `bookmarkName` is the name of the bookmark you want to load. If the bookmark exists in iCloud, its data will be loaded into `bookmarkData`.

   ```
   if let bookmarkData = store.object(forKey: bookmarkName) as? Data {
       // Do something with bookmarkData
   }
   ```

And that's it!

Now, about that NSUserDefaults. NSUserDefaults is another key-value store provided by Apple that allows you to store small amounts of data, but it has some limitations when it comes to synchronization.

For example, NSUserDefaults doesn't automatically synchronize data across devices using iCloud like NSUbiquitousKeyValueStore does. Instead, you would have to implement your own synchronization logic using APIs like NSNotification or KVO.

Additionally, NSUserDefaults is meant to store preferences and settings, not large amounts of data like bookmarks. Using NSUbiquitousKeyValueStore is a better solution for storing bookmarks because it's specifically designed for syncing small amounts of data across devices.

In summary, NSUbiquitousKeyValueStore is a useful tool for storing small amounts of data like bookmarks in iCloud. By following the steps above, you can easily store and access bookmarks across all of your devices without the need for a server.
