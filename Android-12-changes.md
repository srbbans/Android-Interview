# Android 12 Changes for developers

-- https://developer.android.com/about/versions/12/summary

- Approximate location : 
  The dialog has two sets of options, one above the
           other
  Figure 1. System permissions dialog that appears when your app targets Android 12 and requests both ACCESS_FINE_LOCATION and ACCESS_COARSE_LOCATION in a single runtime request.
  When using an app that targets Android 12 or higher, users can request that the app have access to only approximate location information.

  Note: If your app requests ACCESS_COARSE_LOCATION but not ACCESS_FINE_LOCATION, then this change doesn't affect your app.
  If your app targets Android 12 or higher and requests the ACCESS_FINE_LOCATION runtime permission, you must also request the ACCESS_COARSE_LOCATION permission. You must include both permissions in a single runtime request.

  When your app requests both ACCESS_FINE_LOCATION and ACCESS_COARSE_LOCATION, the system permissions dialog includes the following new options for the user, as shown in figure 1:

  Precise: Provides access to precise location information.
  Approximate: Provides access only to approximate location information.

- Custom notifications : 
  Android 12 changes the appearance and behavior of fully custom notifications. Previously, custom notifications were able to use the entire notification area and provide their own layouts and styles. This resulted in anti-patterns that could confuse users or cause layout compatibility issues on different devices.

  For apps targeting Android 12, notifications with custom content views will no longer use the full notification area; instead, the system applies a standard template. This template ensures that custom notifications have the same decoration as other notifications in all states, such as the notification's icon and expansion affordances (in the collapsed state) and the notification's icon, app name, and collapse affordance (in the expansion state). 

- Root launcher activities are no longer finished on Back press : 

  Android 12 changes the default handling of the system Back press on launcher activities that are at the root of their tasks. In previous versions, the system would finish these activities on Back press. In Android 12, the system now moves the activity and its task to the background instead of finishing the activity. The new behavior matches the current behavior when navigating out of an app using the Home button or gesture.

  Note: The system applies the new behavior only to launcher activities that are the root of their tasks—that is, to activities that declare an Intent filter with both ACTION_MAIN and CATEGORY_LAUNCHER. For other activities, the system handles Back press as it did before, by finishing the activity.
  For most apps, this change means that users who use Back to navigate out of your app are able to more quickly resume your app from a warm state, instead of having to completely restart the app from a cold state.

- Microphone and camera indicators : 
  On devices that run Android 12 or higher, when an app accesses the microphone or camera, an icon appears in the status bar.
- Restricted : 
  This bucket, added in Android 11 (API level 30), has the lowest priority (and the highest restrictions) of all the buckets. The system considers your app's behavior, in addition to usage patterns, to decide whether to place your app in the restricted bucket.

  Your app is less likely to be placed in the restricted bucket if your app uses system resources more responsibly. Also, the system places your app in a less restrictive bucket if the user interacts directly with your app.

  If the system places your app in the restricted bucket, the following restrictions apply:

  You can run jobs once per day, in a 10-minute batched session. During this session, the system groups your app's jobs with other apps' jobs.
  Your app can run fewer expedited jobs, compared to when the system places your app in a less-restrictive bucket.
  Your app can invoke one alarm per day. This alarm can be either an exact alarm or an inexact alarm.
  Your app can receive five high-priority Firebase Cloud Messaging (FCM) messages per day in a timely manner. All subsequent FCM messages are delivered with normal priority, so the messages might be delayed if the device is in a power-saving mode.	

  >> Starting in Android 12, this bucket is active by default. The restricted bucket has the lowest priority (and the highest restrictions) of all the buckets. The buckets in order of priority from high to low are:

  Active: App is currently being used or was very recently used.
  Working set: App is in regular use.
  Frequent: App is often used, but not every day.
  Rare: App is not frequently used.
  Restricted: App consumes a great deal of system resources, or may exhibit undesirable behavior.

- UX delay for foreground service notifications :

  To provide a streamlined experience for short-running foreground services, devices that run Android 12 or higher can delay the display of foreground service notifications by 10 seconds, with a few exceptions. This change gives short-lived tasks a chance to complete before their notifications appear.

- All apps in multi-window mode :

  Android 12 makes multi-window mode standard behavior.

  On large screens (sw >= 600dp), the platform supports all apps in multi-window mode regardless of app configuration. If resizeableActivity="false", the app is put into compatibility mode when necessary to accommodate display dimensions.

- Web intent resolution : 
  Starting in Android 12 (API level 31), a generic web intent resolves to an activity in your app only if your app is approved for the specific domain contained in that web intent. If your app isn't approved for the domain, the web intent resolves to the user's default browser app instead.
- Motion sensors are rate-limited : 
  To protect potentially sensitive information about users, if your app targets Android 12 or higher, the system places a limit on the refresh rate of data from certain motion sensors and position sensors.
- App hibernation : 
  Android 12 expands upon the permissions auto-reset behavior that was introduced in Android 11 (API level 30). If your app targets Android 12 and the user doesn't interact with your app for a few months, the system auto-resets any granted permissions and places your app in a hibernation state.
- Safer component exporting : 
  If your app targets Android 12 or higher and contains activities, services, or broadcast receivers that use intent filters, you must explicitly declare the android:exported attribute for these app components.

  Warning: If an activity, service, or broadcast receiver uses intent filters and doesn't have an explicitly-declared value for android:exported, your app can't be installed on a device that runs Android 12 or higher.
  If the app component includes the LAUNCHER category, set android:exported to true. In most other cases, set android:exported to false.
- Specify mutability : 
  If your app targets Android 12 or higher, you must specify the mutability of each PendingIntent object that your app creates. To declare that a given PendingIntent object is mutable or immutable, use the PendingIntent.FLAG_MUTABLE or PendingIntent.FLAG_IMMUTABLE flag, respectively.

  If your app attempts to create a PendingIntent object without setting either mutability flag, the system throws an IllegalArgumentException, and the following message appears in Logcat 
  Strongly consider using FLAG_IMMUTABLE, only use FLAG_MUTABLE if \
some functionality depends on the PendingIntent being mutable, e.g. if \
it needs to be used with inline replies or bubbles.

