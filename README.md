
# DZFICNetworkController
Plug &amp; Play Network Controller for FastImageCache by Path.

[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
----  
[FastImageCache][1] by Path is an incredible Image Caching library for iOS apps. However, you may have noticed that downloading images from the network is your responsibility. DZFICNetworkController is a simple class that conforms the FIC’s delegate protocol and handles all the networking for you. 

### Usage
It’s really simple.

```objc
DZFICConfiguration *config = [DZFICConfiguration new];
config.maxConcurrentConnections = 50;
config.shouldFollowRedirects = NO;
config.shouldContinueInBackground = YES;
    
self.networkController = [[DRFICNetworkController alloc] initWithConfiguration:config];

[FICImageCache sharedImageCache].delegate = self.networkController;
```

### Adding it to your project
We recommend using Carthage to add `DZFICNetworkController` to your project. Simply add the following to your Cartfile
```yaml
github "dzns/DZFICNetworkController"
```

then run, `carthage update` to grab the latest source. 

### How it works
`DZFICNetworkController` utilizes the `sourceImageURLWithFormatName:` method on your `id<FICEntity>` object to fetch a URL for the image to be downloaded. No extra efforts required.

[1]: https://github.com/path/FastImageCache.git

### License
MIT License. Please refer to the LICENSE file for more details.

### Author & Copyright
Nikhil Nigade  
© 2014 - 2015 Dezine Zync Studios LLP. - All Rights Reserved.
