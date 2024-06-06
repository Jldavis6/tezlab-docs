# Running the TezLab App Through Terminal

**Warning**: Before going any further, ensure that you have downloaded all the software outlined in [this guide](software.md). Additionally, it would be wise to `cd` into your `tesla-mobile` directory.

Now that you're all set up, here is an (admittedly brute-force) way to build and run the TezLab app in a simulator.

### Updating system files

Using `echo -n`, pipe the following into your `~/.netrc` file:
```
machine api.mapbox.com
    login mapbox 
    password sk.ey...
```
For the full password, ask Andy or Perlman.

Also with `echo -n`, add `MAPBOX_DOWNLOADS_TOKEN=sk.ey...` (again, ask for the full password) to `~/.gradle/gradle.properties`.

This all provides the infrastructure needed to run a functioning copy of TezLab's charger map.

### npm install

Now that you've added those secrets to your system, run `npm install --force`. This is a decidedly inelegant tactic, but it may be necessary given the assortment of deprecated and end-of-life software used by the TezLab app at the time of writing this guide. The `--force` flag ignores any software incompatibilities or deprecations, though do note you may be able to get away with `--legacy-peer-deps` instead. Feel free to try `npm install` first, but in the likely event that it fails, add one of the aforementioned flags.

### Installing pods

From `.../tesla-mobile'`, run `cd ios`, then `pod install` (if you haven't already, or if you've already run `pod deintegrate`; else, best to just go for `pod deintegrate && pod install`). This will install all the dependencies outlined in `tesla-mobile/ios/Podfile`.

### npm start

You should now be in the `ios` subdirectory. `cd` into the parent `tesla-mobile` directory, then run `npm start`. This command, which is equivalent to `npx react-native start --reset-cache`, will begin the process of booting up the app.

### npm run run-ios-dev

In a **new terminal window**, `cd` into `tesla-mobile`. From there, run `npm run run-ios-dev`. This script will launch the iOS app in a simulator. From there, you should be able to play with the app on your Mac as you would on your phone!



If you've made it this far, you've successfully run the proxy TezLab app! Congratulations, and I hope this guide has been of assistance!
