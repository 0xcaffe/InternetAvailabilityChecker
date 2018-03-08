## InternetAvailabilityChecker
This project checks if active internet is present or not on device. Connecting to network doesn't mean internet access so this project pings google to check if internet is present or not

# Overview

Forked from:
https://github.com/AggarwalAnkit/InternetAvailabilityChecker

I added a couple of modifications.


Get it by adding to your `build.gradle` file:
```groovy
implementation 'com.0xcaffe:internetavailabilitychecker:1.0.5'
```


### Usage
Within an `Application` class call:

```kotlin
InternetAvailabilityChecker.init(this)
```

#### Register a callback
```kotlin
InternetAvailabilityChecker.getInstance()
	.addInternetConnectivityListener {
                Log.d(TAG, "isOnline = $it")
            }
```

#### Remember to unregister in your `onDestroy` function:
```kotlin
override fun onDestroy() {
        super.onDestroy()
	InternetAvailabilityChecker.getInstance()
		.removeAllInternetConnectivityChangeListeners()
}
```