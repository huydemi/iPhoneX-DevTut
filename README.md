# iPhoneX-DevTut

In this tutorial, you’ll explore the new aspect ratio, and build an app with a search controller integrated into the navigation bar.

Then you’ll explore how to fix an app that was created shortly before the iPhone X announcement: is it enough to just turn on safe area? Read on to find out.

![screenshot](https://koenig-media.raywenderlich.com/uploads/2017/10/DesigningiPhoneX-feature-1.png)

---

# Notes

![screenshot](https://koenig-media.raywenderlich.com/uploads/2017/10/AspectRatioSample.png)

**Rule**: Compose your images so you don’t lose important visual information when Aspect Fill crops them.

### Designing a New App

![screenshot](https://koenig-media.raywenderlich.com/uploads/2017/10/NewCandySearch0-231x500.png)

**Rules**

- Avoid the sensor housing and home indicator, except for background image and vertically scrollable views.
- Avoid placing controls where the home indicator overlaps, or corners crop.
- Don’t hide or draw attention to sensor housing, corners or home indicator.

### Use Auto Layout

![screenshot](https://koenig-media.raywenderlich.com/uploads/2017/10/UseSafeArea.png)

**Rules**

- Use safe area layout guides.
- Use margin layout guides.
- Center content or inset it symmetrically.

### Use Standard UI Elements

![screenshot](https://koenig-media.raywenderlich.com/uploads/2017/10/NewCandySearchLandscape-650x300.png)

![screenshot](https://koenig-media.raywenderlich.com/uploads/2017/10/NewCandySearch_8.png)

**Recommendation**: Use standard UI elements.

**Note**: The iPhone X is compact width in landscape orientation, so it behaves like the iPhone 8, not the 8 Plus.

### Status Bar

- The iPhone X status bar is higher, so dynamically position content based on the device type, instead of assuming a fixed 20-pt height.
- Always show the status bar unless hiding it adds real value to your app.

### 3x Screen Resolution

- Use PDF for flat vector artwork; provide @3x and @2x of rasterized artwork.
- An app doesn’t use 3x if it doesn’t have a LaunchScreen.storyboard.

### Home Indicator Special Cases

- If your app uses the swipe-up-from-bottom gesture, turn on edge protect with preferredScreenEdgesDeferringSystemGestures(): the user must swipe up twice to access the home indicator.
- If your app includes passive viewing experiences, turn on auto-hiding with prefersHomeIndicatorAutoHidden(): the home indicator fades out if the user hasn’t touched the screen for a few seconds, and reappears when the user touches the screen.

### iPhone X Simulator vs Device

- Use the simulator to check portrait and landscape layout.
- Use an iPhone X device to test wide color imagery, Metal, front-facing camera.

### Other Stuff

- Don’t reference Touch ID on iPhone X. Don’t reference Face ID on devices that support Touch ID.
- Don’t duplicate system-provided keyboard features like Emoji/Globe and Dictation buttons.

### Updating an Existing App

What if you want to update an existing app for iPhone X? 

- First, update its assets, including background images, to PDF or add @3x images. 
- Then make sure it has a LaunchScreen.storyboard, and turn on Safe Area. 
- Safe area layout guides change top, bottom and edge constraints, so check these, and fix them if necessary.

- Check for any layout that depends on a 20-pt status bar or 44-pt tool bar, and modify it to allow for different heights. Or, if your app hides the status bar, consider unhiding it for iPhone X.

- Next, set View as to iPhone X, and check every layout configuration. Move controls away from the edges, corners, sensor housing and home indicator.

- Consider integrating search view controllers into the navigation bar.

- Build and run the app on the iPhone X simulator, and check every layout configuration. In landscape, check that table view cell and section header content is inset, but the background extends to the edges.



---

Source:

- [Development Tutorial for iPhone X](https://www.raywenderlich.com/173928/develop-design-iphone-x)
