# Sense - iOS SDK 

Sense is a device intelligence and identification tool. This tool collects a comprehensive set of attributes unique to a device or browser, forming an identity that will help businesses.

## Requirements
    * iOS 12.0 or above
    * Swift version 5.0 and above

### Step 1 - Installation
```
pod 'SenseOSUserActivity', '~> 0.0.2'
pod update
```
### Step 2 - Import SDK
```
import SenseOSUserActivity
```
To initialize the SDK add the below line of code.

## To get Behaviour Data for Keystrokes, Mouse Movements, Scroll Metrics, Touch Metrics, you can add the below methods to initialize it.

### For Keystrokes, pass your textfields as arguments like below

```
@IBOutlet weak var txtUsername: UITextField
@IBOutlet weak var txtPassword: UITextField

SenseOSUserActivity.initKeyStrokeBehaviour(for: [txtUsername, txtPassword]);
```

### For Scroll Metrics

```
@IBOutlet weak var scrollView: UIScrollView

SenseOSUserActivity.initScrollBehaviour(for: [scrollView]);
```

### For Touch Metrics

```
SenseOSUserActivity.initTouchBehaviour(for: self.view)
```

### To get Behaviour Data, Call below method to get it

```
SenseOSUserActivity.getBehaviourData(withDelegate: self)

extension ViewController: SenseOSUserActivityDelegate{
    func onFailureBehaviour(message: String) {
        print("Failure data")
    }

    func onSuccessBehaviour(data: String) {
        print("Success data")
    }
}
```
