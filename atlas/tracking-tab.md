# Tracking Tab Repo Navigation

Intimidated by the glut of files in tesla-mobile? Have no fear – the layout is "laid out" (mostly) right here!

Note: This guide, as with the others in this subdirectory, was made on July 10, 2024; as such, those reading this may find that some aspects of the app don't quite adhere to the structure enumerated here.

Now let's get to it. You'll see here, in a DFS style, a list of all the screens, graphs, and pages readily accessible from the Profile tab, in the format of "What you're looking at" – "Where to find it in the repo". Here goes...

**Homepage** (by default, starts on *Activity* Tab) - `tracking/Tracking.js`
- **Export Header** - `tracking/ExportsHeader.js`
  - **Exports** - `tracking/TrackingExports.js`
- **Current Drive** - `shared/CurrentTripDashboard.js`
- **Current Charge** - `shared/CurrentChargeReportCard.js`
- **Filter and Summarize** - `tracking/Summary/index.js`
  - **Filter Screen** - `tracking/FilterScreen/index.js`
- **Timestamps Above Usage Maps** - `util.js.returnSection`
- **Usage/Usage Map** - `shared/Cards/Usage.js` and `shared/Cards/UsageMap.js`
  - **Usage Report** (click on Usage/Usage map) - `profile/ChargeReportScreen/index.js`
- **Drive Banners** (i.e. leaf icon --> Brooklyn, NY to Brooklyn, NY --> 1.0 mi) - `tracking/TrackingBatteryUsage/DriveCard.js`
  - **Drive Details** (double click/press and hold drive banner) - `shared/DriveDetailsModal/index.js`
    - **Stats** - `shared/DriveDetailsModal/Card.js`
- **Charge Card** - `shared/Cards/Charge.js`
- **Export** - `shared/ExportButton.js`
- **New Post** - `social/NewPostModal/index.js`
