[![NPM version](https://img.shields.io/npm/v/community-cordova-plugin-ram)](https://www.npmjs.com/package/community-cordova-plugin-ram)


# community-cordova-plugin-ram 

I dedicate a considerable amount of my free time to developing and maintaining many cordova plugins for the community ([See the list with all my maintained plugins][community_plugins]).
To help ensure this plugin is kept updated,
new features are added and bugfixes are implemented quickly,
please donate a couple of dollars (or a little more if you can stretch) as this will help me to afford to dedicate time to its maintenance.
Please consider donating if you're using this plugin in an app that makes you money,
or if you're asking for new features or priority bug fixes. Thank you!

[![](https://img.shields.io/static/v1?label=Sponsor%20Me&style=for-the-badge&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/eyalin)


---

# Community Cordova Plugin RAM

## Overview
This Cordova plugin provides a way to access RAM (memory) information of the mobile device. It supports both Android and iOS platforms, returning the total, used and free memory as well as the current usage percentage.

## Installation
To install the plugin in your Cordova project, use the following command:
```
cordova plugin add community-cordova-plugin-ram
```

## Usage
To use the plugin, call the `getRAMInfo` method. This method is asynchronous and returns a Promise that resolves with the RAM information.

```javascript
document.addEventListener('deviceready', onDeviceReady, false);

function onDeviceReady() {
    RamPlugin.getRAMInfo().then(function(info) {
        console.log('RAM Information:', info);
    }).catch(function(error) {
        console.error('Error getting RAM information:', error);
    });
}
```

### API

#### getRAMInfo()
Returns a Promise that resolves with an object containing RAM information. The response object is the same on both Android and iOS and includes:

- `totalRAM`: The total physical RAM available on the device, in bytes.
- `usedRAM`: The amount of RAM that is currently in use, in bytes.
- `freeRAM`: The amount of free RAM available for use, in bytes.
- `ramUsagePercent`: The percentage of RAM usage, calculated as `(usedRAM / totalRAM) * 100`.

## Platform Specifics
- **Android**: Returns total, used and free RAM (in bytes) and the usage percentage.
- **iOS**: Returns the same set of values (total, used and free RAM in bytes and the usage percentage).

## Contributing
Contributions to the plugin are welcome. Please ensure to follow the coding standards and submit your pull requests for review.

## License
This project is licensed under the MIT License.

---
[community_plugins]: https://github.com/EYALIN?tab=repositories&q=community&type=&language=&sort=
