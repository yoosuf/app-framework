# App Framework - Documentation

> First contact with App Framework? Please read the [Readme file](README.md) first!

Read less, code more - please open a ticket for any open question in our [Issue List](https://github.com/scriptPilot/app-framework/issues).

### Required knowledge

- [Node.js with npm](https://docs.npmjs.com/getting-started/what-is-npm)
- [Framework7](https://framework7.io/docs/) / [Framework7-Vue](https://framework7.io/vue/)

Optional

- [Vue](https://vuejs.org/v2/guide/)
- [Firebase](https://firebase.google.com/docs/web/setup)

### Setup your development environment

- Install [Node.js with npm](https://docs.npmjs.com/getting-started/what-is-npm)
- Download *[package.json](https://raw.githubusercontent.com/scriptPilot/app-framework/master/demo-app/package.json)* file to an empty folder (keep extension .json!)
- Run `npm install` to setup project folder
- Run `npm update` to update *App Framework* to latest sub version

### Design your application
- Use our printable [smartphone template](media/smartphone-template.pdf) to sketch your application
- Use our icon template as [PDF to sketch](media/icon-template.pdf) and [PPTX to draw](media/icon-template.pptx) your application icon

### Develop your application

- Update the configuration in *package.json* file - first of all for Firebase!
- Run `npm run dev` to start development server at localhost:8080
- Save images to *images* folder
- Edit app component in *app.vue* file
- Edit page components in *pages* folder
  - After adding, removing or renaming pages you have to run `npm run dev` again!
  - Study the code of the example pages to learn how to realize things in App Framework
- Edit [database rules](https://firebase.google.com/docs/database/security/quickstart) in *database-rules.json* file
- Edit [storage rules](https://firebase.google.com/docs/storage/security/) in *storage-rules.txt* file

### Test your application

- Run `npm run check` to check files according [Standard JavaScript](http://standardjs.com/index.html)
- Run `npm run fix` to fix files as far as possible according [Standard JavaScript](http://standardjs.com/index.html)
- Use [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/) to debug your application

### Build your application

- If you use Git, commit your changes first
- Run `npm run icons` to update favicon, icons and splash screen graphics
- Run `npm run patch` after bugfixes and improvements
- Run `npm run minor` after adding new functionality
- Run `npm run major` after breaking backward-capability

### Deploy your application

*App Framework* does many adjustments in the background to enable you to deploy your App easily as Web App or as native App. So you could start fast and become professional later on without any change. But what are the differences?

||Web App|Native App|
|---|---|---|
|Installation|Are running in the device browser and could be pinned to the homescreen.|Are installed from an App Store or manually to the device (Android only).|
|Performance|Reload on reopen, but could be cached for offline usage. Offline warning.|Kept in runtime of the device, smoother usage. No offline warning.|
|Capability|Only browser features.|Access to the device hardware and OS features.|
|Deployment|In seconds.|Additional native build plus approval process, which takes some time and could be refused at the Apple App Store.|
|Costs|Firebase hosting service is free for small apps.|Apple requires developer program (around 99€ per year), Google Play store requires registration fee (around 25 USD once). For selling apps, Apple and Google charge around 30% of the sales.|
|Promotion|All regular ways.|All regular ways plus special promotions and user ratings in the store.|

Deployment to your own server (Web App)

- Upload the latest *www/build* folder to your server and then the *www/.htaccess* file
- For rollback: Change the version in *www/.htaccess* file to the previous one and upload it to your server

Deployment to [Firebase Hosting](https://firebase.google.com/docs/hosting/) (Web App)

- Run `npm run database` to overwrite the Firebase database rules with the content of *database-rules.json*
- Run `npm run storage` to overwrite the Firebase storage rules with the content of *storage-rules.txt*
- Run `npm run hosting` to push newest build to Firebase Hosting
- For rollback: Change the version in *www/.htaccess* file to the previous one and run `npm run hosting`

Deployment to the Apple App Store (native App)

- You need a Mac with [macOS](http://www.apple.com/de/macos/) and installed [Xcode](https://developer.apple.com/xcode/) (free)
- You need to sign to the [Apple developer program](https://developer.apple.com/programs/) (around 99€ per year)
- You need to prepare the publishing in [iTunes Connect](https://itunesconnect.apple.com/)
- Run `npm run ios` to create a project file for Xcode, based on [Cordova](https://cordova.apache.org/)
- Test your application on several device simulators
- Make screenshots on the biggest iPhone (you will need them in iTunes Connect later on)
- Create an archive of the Xcode project and upload it within Xcode to iTunes Connect
- Send your App in iTunes Connect for the review to Apple

Deployment to the Google Play Store (native App)

- You need to install the [Android Studio](https://developer.android.com/studio/)
- You need to register at the [Google Play Developer Console](https://play.google.com/apps/publish/signup/) (around 25 USD once)
- Run `npm run android` to create a project file for Android Studio, based on [Cordova](https://cordova.apache.org/)
- Select your project, confirm Gradle sync and test your application on several device simulators
- Make screenshots, you will need them later in the Google Play Developer Console
- Generate signed APK
- Log in to the Google Play Developer console to deploy your application

### Backup your application

- Run `npm run backup` to save the Firebase database content to *database-backup.json* file
- Run `npm run zip` to save your project files and latest build to a zip file
- Backup your project folder frequently by
 - Moving the zip file to any external drive or cloud
 - *and/or* Pushing and synchronizing your changes to GitHub
