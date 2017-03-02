
# dash for iOS

	* [Installation Instructions](https://kapeli.com/dash_ios?ref=mac#install)

	You can use Xcode 8 to install Dash on your iOS device using just your Apple ID.

	All you need to do is:

		* Install [Xcode 8](https://developer.apple.com/download/)
		* Download the Dash for iOS [Source Code](https://github.com/Kapeli/Dash-iOS/releases/tag/v1.6.0)
		* Open "Dash iOS.xcworkspace" in Xcode
		* Open Xcode's Preferences > Accounts and add your Apple ID
		* In Xcode's sidebar select "Dash iOS" and go to Targets > Dash > General > Identity and add a word to the end of the Bundle Identifier to make it unique. Also select your Apple ID in Signing > Team
		* Connect your iPad or iPhone and select it in Xcode's Product menu > Destination
		* Press CMD+R or Product > Run to install Dash
		* If you install using a free (non-developer) account, make sure to rebuild Dash every 7 days, otherwise it will quit at launch when your certificate expires
