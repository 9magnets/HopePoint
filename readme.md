## Hope Point by 9magnets, LLC

Ever need an easy way to spoof locations on your physical iPhone, iPad, or Apple TV to pretend that the device is somewhere you currently are not? Maybe you're like us, and you've built an application that requires location services, and you need to test it your development work? Would you prefer to not jailbreak your phone in order to do this?

Let me introduce you to Hope Point. We've been building a location-based application, and with this, needed a way to fake our device's location in order to better mimic what we would see out in the real world. Hope Point was a quick way for us to trick our physical iPhones and iPads into believing we were in Point Hope, Alaska, or one of several other test locations we needed. We've used this method directly into our project for testing, but we've created a sample project here so that you can spoof your device's location for testing, and copy our work for integration into your own testing. It's a simple addition of a GPX file into a standard Xcode Scheme launch option. But if you're a novice developer, you may have never heard about this valuable iOS tool. To help, we've built this sample repo for you to learn and test with.

So if you need a way to make your iPhone, iPad, or Apple TV think it's in Alaska, New York, London, Chicago, or any other city worldwide, just clone this repository and you're halfway there.

### Steps 

1) Clone this repository, or [download the ZIP of the latest source code](https://github.com/9magnets/HopePoint/archive/master.zip) directly from from GitHub.

2) Make sure that you have the latest version of Xcode installed on a Macintosh computer. It is available from the Mac App Store. This application will not work through an AdHoc build, so you will need a Mac and Xcode to install directly. After you've downloaded the code, open hopepoint.xcodeproj if you need this app to work with an iPhone or iPad. Or open highpoint_tv.xcodeproj if you want to spoof location on an Apple TV. If you'd like to swap quickly between iOS or tvOS devices, open highpoint.xcworkspace, and flip between schemes.

3) Connect the iPhone, iPad, or Apple TV that you would like to spoof a location with to your Macintosh. 

4) You'll likely need to change the application's Bundle Identifier. Currently it is com.9magnets.hopepoint. Change this to com.whateveryouwant.hopepoint, and you should be good.

5) In the Xcode project navigator, choose your device from the Scheme toolbar menu. Then click on the Run button. The first time you run the app, you may need to allow Xcode to set up a proper signing and provisioning. If prompted with "Fix It", feel free to hit Yes, and you should be good to go. 

6) Hope Point should run on your iPhone, iPad, or Apple TV, and using the default GPX file, your device's location services should set your current location as Point Hope, Alaska, when you use Maps.app, or any other application that uses location services. To test, we typically launch the Maps app before we launch the app we are testing, to verify that it correctly reports us in the proper city. If your device does not update, and continues to have you at your actual physical location, skip below to Step 7.
  
  * A troubleshooting tip, if your location does not change, automatically, try the following. From the Edit Scheme option in the Xcode project navigator, Edit the Options under the Run/Debug to set Point Hope (or whatever location you prefer) as the default location for location services at app launch time. For more information on how to do this, see [this Apple iOS Developer document](https://developer.apple.com/library/ios/recipes/xcode_help-scheme_editor/Articles/simulating_location_on_run.html#//apple_ref/doc/uid/TP40010402-CH10).

7) If you need to change your location from Point Hope to a different city or if the app does not automatically set your city, use Xcode's Debug menu. Once in the Debug menu, scroll down to Simulate Location, and select a different city or add a new GPX file to the workspace. We've included our common test cities inside the workspace's Supporting Files. 

8) Do you need to have your device continue to fake your location while not connected to Xcode? This was important for us, as we often had to do testing and spoof our iOS device's location when not connected for debugging. If so, DO NOT stop the project in Xcode, and instead just disconnect your device from your computer's USB port. You should receive an error from Xcode that device connection has been lost. This is expected, just hit OK.

9) Your device should continue to report Point Hope, Alaska in location services for a significant period of time, potentially as long as until the iPhone, iPad, or Apple TV is restarted. Take note of this, if you go to use your device for directions, mapping, or any other third-party app that uses location services, as your device will be inaccurate and may cause you some headache. For example, if your device time is set to change automatically based upon your current location, your device will soon change it's clock to the Alaska Time Zone.

10) Location change back to your actual location? Just connect your iOS device back to your Mac, launch Xcode, and hit run.

As this location spoofing method does not have a considerable amount of documentation, we can't say exactly how long your device will remain in the spoofed location. We've seen it last several days, but your mileage may vary. Eventually, you'll want your actual location back, and a device restart should resolve this.

Good luck, and happy spoofing! Hope this helps out with your location sensitive iOS apps!