# Profile Tab Tesla-Mobile Navigation

Intimidated by the glut of files in `tesla-mobile`? Have no fear – the layout is "laid out" (mostly) right here!

*Note*: This guide, as with the others in this subdirectory, was made on July 10, 2024; as such, those reading this may find that some aspects of the app don't quite adhere to the structure enumerated here.

Now let's get to it. You'll see here, in a DFS style, a list of all the screens, graphs, and pages readily accessible from the Profile tab, in the format of `"What you're looking at" – "Where to find it in the repo"`. Here goes...

- **Homepage** (where you scroll) – `profile/HomeScreen/index.js`
  - *Top Bar*
    - **User Profile** (click on profile picture) – `user_profile/UserProfile/index.js`
      - **Settings** (settings gear > `Settings & Preferences`) - `profile/Settings/index.js`
        - **Edit Profile** (click Edit/pencil icon) - `profile/Settings/EditInfoModal.js`
        - **Subscription** - `profile/Subscription.js`
        - **Base Currency** (under Personalize) - `profile/Settings/CurrencySetting.js`
        - **Fuel Consumption Units** - `profile/Settings/FuelEffSetting.js`
        - **Fuel Comparison Price** - `profile/Settings/FuelPriceSetting.js`
        - **Temperature Units** - `profile/Settings/TemperatureSetting.js`
        - **Distance Units** - `profile/Settings/DistanceSetting.js`
        - **Use Plain App Startup** - `profile/Settings/SplashVideoSetting.js`
        - **Current Vehicle** (under Vehicle Settings) - `profile/Settings/SwitchVehicleSection.js`
        - **Vehicle Fuel Economy Comparison** - `profile/Settings/VehicleFuelEffSetting.js`
        - **Notifications** (click `Manage Notifications`) - `profile/NotificationSettings/index.js`
        - **Welcome Wagon** (click `View Welcome`) - `shared/WelcomeWagon.js`
        - **Redeem a Gift** (click `Redeem Gift`) - `marketing/GiftModal.js`
        - **Support & Contact** - `shared/HelpBeacon.js`
        - **Change Password** - `profile/Settings/ResetPasswordModal.js`
        - **Privacy** - `profile/PrivacyView.js`
        - **Terms of Service** - `profile/TermsView.js`
        - **Log Out** - `profile/Settings/index._confirmLogout`
        - **Delete Account** - `profile/Settings/index._confirmDeleteStep(1/2)/deleteAccount`
      - **Car Image** - `shared/CarImage.js`
      - **Profile Header** (name, car, subscription type, bio, etc) - `user_profile/UserProfile/HeaderSection.js`
        - **Edit Bio** - `user_profile/UserProfile/EditBioModal.js`
        - **Followers** - `user_profile/UserProfile/FollowersScreen.js`
        - **Following** - `user_profile/UserProfile/FollowingScreen.js`
      - **Switch Vehicle** (press `All Cars` if applicable) - `shared/VehicleMenu.js`
      - **Stats** (`View Statistics`) - `profile/Stats.js`
      - **New Post** (Click comment icon with +) - `social/NewPostModal/index.js`
    - **Pill Button** (e.g. "Offline", "Driving", "Charging") - `shared/PillButton/index.js`
  - **Add Car Image/"Your Vehicle is Disconnected"** - `profile/HomeScreen/VehicleImage.js`
  - **Switch Vehicle** (if applicable) - `shared/SwitchVehicleMenu.js`
  - **Range Settings Menu** (click lock/sentry icon/battery, range) - `profile/HomeScreen/RangeSettingsMenu.js`
  - **Current Drive** - `shared/CurrentTripDashboard.js`
  - **Current Charge** - `shared/CurrentChargeDashboard/index.js`
  - **Controls** - `controls/MiniControls.js`
  - **Notification Card** - `profile/HomeScreen/NotificationsPane.js`
    - **Notification Page** - `profile/Notifications.js`
      - **Menu** (three dots) - `profile/Notifications.js`
  - **Recently Tracked** - `profile/HomeScreen/Recent.js`
    - **Drives** - `shared/Cards/Drive.js`
    - **Charges** - `shared/Cards/Charge.js`
  - **Stats** (`View Statistics`) - `profile/Stats.js`
  - **Usage Report** - `profile/ChargeReportScreen/index.js`
    - **Upgrade Button** - `marketing/UpgradePillButton.js`
    - **Battery Level** - `profile/ChargeReportScreen/ProReportSection.js`
      - **Graph** - `graphs/ChargeReportGraph.js`
    - **Usage Breakdown** - `graphs/UsageBreakdownGraph.js`
  - **You Vs. Others** - `profile/EffVsOthersScreen.js`
  - **Badges** - `profile/BadgesInfo.js`
    - **Individual Badge** - `profile/BadgeTimeline.js`
  - **Sustainability Report** - `profile/SustainabilityReportScreen/index.js`
    - **More Information** - `profile/ForestsExplained.js`
    - **Buy Trees** (`Plant Trees` or `Carbon Neutral`) - `profile/PurchaseTrees/index.js`
    - **Tree Map** - `maps/TreeMap.js`
    - **Carbon Impact Graph** - `profile/SustainabilityReportScreen/SustainabilitySlider.js`
  - **Trends** - `profile/TrendsScreen.js`
    - **Range Comparison** - `stat_charts/RangeComparison.js`
    - **Battery Performance** - `stat_charts/BatteryPerformance.js`
    - **Temperature vs. Efficiency** - `stat_charts/TemperatureEfficiency.js`
