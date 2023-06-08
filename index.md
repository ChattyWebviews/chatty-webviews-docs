---
title: Getting started
layout: home
---

# Getting Started with Chatty Webviews

Welcome to Chatty Webviews, a simple and effective framework designed to facilitate communication between your native classes and webviews in your mobile applications.

## Requirements

Before we get started, make sure you have the following:

For iOS:
- iOS 11.0+
- Swift 5.0+

For JavaScript:
- A JavaScript project with npm installed

## Installation

### iOS

Chatty Webviews for iOS is available through [CocoaPods](https://cocoapods.org). 

To install it, add the following line to your Podfile:

```ruby
pod 'ChattyWebviews'
```

Then run `pod install` in your project directory.

### JavaScript
To install Chatty Webviews for JavaScript, run the following command in your project directory:
```
npm install @chatty-webviews/js
```

## Basic Usage
After installation, you can start using Chatty Webviews in your project.

### iOS
Import ChattyWebviews and initialize your webview view controllers. An example of this process is shown below:
```
import ChattyWebviews

class MainTabBarViewController: UITabBarController {
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        let scheduleVC = WebViewFactory.createWebview(localFolder: "www", path: "/schedule")
        scheduleVC.tabBarItem = UITabBarItem(title: "Schedule", image: nil, tag: 0)
        scheduleVC.messageDelegate = self
        
        // Additional setup code...
    }
}
```

To receive messages from the webviews, conform to the **CWMessageDelegate** protocol.


```
extension MainTabBarViewController: CWMessageDelegate {
    
    func controller(_ controller: ChattyWebviews.CWViewController, didReceive message: ChattyWebviews.CWMessage) {
        print(message.topic)
        let msg = CWMessage(topic:"mife-a", body: ["msg":"done"])
        controller.sendMessage(msg)
    }

}
```

### JavaScript
In your JavaScript code, call the **attach** method at the starting point of your module where you need to subscribe for or send messages.

```
import { attach } from '@chatty-webviews/js';

export class AppComponent {
  constructor() {
    attach();  
  }  
}

```

To subscribe for incoming messages, use the **subscribe** method:

```
import { subscribe, ChattySubscription } from '@chatty-webviews/js';

export class HomeComponent implements AfterViewInit, OnDestroy {
  
  chattySubscription: ChattySubscription

  ngAfterViewInit(): void {
    chattySubscription = subscribe('update-items', (msg: any) => {
      console.log(msg);
    })
  }
  
  ngOnDestroy() {
    chattySubscription.unsubscribe()
  }
}
```

To send messages, use the **sendMessage** method:

```
import { sendMessage } from '@chatty-webviews/js';

export class HomeComponent implements AfterViewInit {

  fetchItems(limit: number) {
    sendMessage("get-items", {limit});
  }
}
```

## Next Steps

After setting up Chatty Webviews and familiarizing yourself with its basic functions, check out the other sections of our documentation for more detailed information on all the features Chatty Webviews has to offer.

