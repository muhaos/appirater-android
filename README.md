Introduction
------------
This is a modified version of
   https://github.com/kenyee/appirater-android

These are new features of this fork:
   - Now appirater do show question if user likes app or not, if user does then show "rate us" dialog, otherwise open mail composer to leave feedback

Set up
-------------------------
0. Download this repo and add as "Gradle project" to android studio
1. Copy the /res/values/appirater-settings.xml from the AppiraterAndroid library in to your projects /res/values/ folder and adjust the settings to your preference.
2. Add Appirater.appLaunched(this); to the onCreate method in your main Activity.

appirater-settings.xml
-----------------------
These are all the settings that can be configured via the xml file:
 - appirater_app_title: your app name
 - appirator_enjoy_message: prompt if user enjoy app 
 - appirator_button_enjoy_yes: text for yes button
 - appirator_button_enjoy_no: text for no button
 - appirator_feedback_email: mail to send feedback if user select no
 - appirator_feedback_email_title: email subject
 - appirater_rate_title: dialog title string
 - appirator_message: prompt for rating app
 - appirator_market_url: URL to app store to rate your app
 - appirator_days_until_prompt: days until it prompts you
 - appirator_launches_until_prompt: #launches until it prompts
 - appirator_untimed_events_until_prompt: #events until it prompts (no time limit)
 - appirator_timed_events_until_prompt: #events until it prompts but only after appirator_launches_until_prompt has been hit
 - appirator_button_rate: text for Rate Now button
 - appirator_button_rate_later: text for Later button
 - appirator_button_rate_cancel: text for Don't Rate button
 - appirator_days_before_reminding: #days before it reminds you after you press Later
 - appirator_test_mode: if set to "true", will show you dialog immediately for testing
 - appirator_button_start_color: gradient start color for buttons
 - appirator_button_end_color: gradient end color for buttons
 - appirator_button_text_color: button text color
 - appirator_title_color: title/divider color

Analytics Callback
------------------
There was a need for analytics callbacks for the buttons user clicked in the rating prompt dialog, so the RatingButtonListener interface was added.
You can add this support in the appLaunched() call as the second parameter; you'll get calls to the onRate, onLater, and onDeclined methods when users click them.  If you have no need for this, pass in null instead.
