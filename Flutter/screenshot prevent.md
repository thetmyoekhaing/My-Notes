
### Android (in MainActivity)
```kotlin
import android.os.Bundle  
import android.view.WindowManager  
import io.flutter.embedding.android.FlutterActivity  
  
class MainActivity: FlutterActivity() {  
    override fun onCreate(savedInstanceState: Bundle?) {  
        super.onCreate(savedInstanceState)  
        // below line prevents the user from taking screenshot or record the screen  
        window.setFlags(WindowManager.LayoutParams.FLAG_SECURE, WindowManager.LayoutParams.FLAG_SECURE)  
    }  
}
```

### Ios (in App Deligate)

```swift
import UIKit  
import Flutter  
  
@UIApplicationMain  
@objc class AppDelegate: FlutterAppDelegate {  
    override func application(  
        _ application: UIApplication,  
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?  
    ) -> Bool {  
        GeneratedPluginRegistrant.register(with: self)  
        // Add the code to prevent screenshots  
        if let window = self.window {  
            window.isSecure = true  
        }  
        return super.application(application, didFinishLaunchingWithOptions: launchOptions)  
    }  
}
```
