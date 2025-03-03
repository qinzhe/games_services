[![pub package](https://img.shields.io/pub/v/games_services.svg)](https://pub.dartlang.org/packages/games_services)

<img src="https://github.com/Abedalkareem/games_services/raw/master/logo.png" width="200"/>

A Flutter plugin to support game center and google play games services.  

## Screenshot  
#### iOS  
<img src="https://raw.githubusercontent.com/Abedalkareem/games_services/master/screenshots/screenshot1.png" width="200"/> <img src="https://raw.githubusercontent.com/Abedalkareem/games_services/master/screenshots/screenshot2.png" width="200"/> <img src="https://raw.githubusercontent.com/Abedalkareem/games_services/master/screenshots/screenshot3.png" width="200"/>  
#### Android  
<img src="https://raw.githubusercontent.com/Abedalkareem/games_services/master/screenshots/screenshot4.png" width="200"/> <img src="https://raw.githubusercontent.com/Abedalkareem/games_services/master/screenshots/screenshot5.png" width="200"/>  

## Tutorials  

[Written tutorial](https://bit.ly/2yv1C00)  

Video tutorial
*Will be added soon.*  

## Apps  

Monkey Banana [Android](https://play.google.com/store/apps/details?id=com.jostudio.monkeybanana) & [iOS](https://apps.apple.com/gm/app/id1514479049) by Abedalkareem.  
[Nonogram Colors](https://play.google.com/store/apps/details?id=com.tbuonomo.nonogramcolordot) by @tommybuonomo.  
[Ripple Effect Puzzle](https://play.google.com/store/apps/details?id=com.tbuonomo.rippleeffectpuzzle) by @tommybuonomo.  
Lights: A Memory Game [Android](https://play.google.com/store/apps/details?id=us.leephillips.lights) & [iOS](https://apps.apple.com/us/app/lights-a-memory-game/id1580230611) by @theLee3.  


## Usage  
#### Sign in  
Sign in the user to the Game center (iOS) or Google play games services (Android). You should call the sign in before making any action (like sending a score or unlocking an achievement).  
``` dart
 GamesServices.signIn();
```  

#### Silent Sign in
``` dart
 GamesServices.silentSignIn();
``` 

#### Is Signed In
A boolean value to check to see if the user is currently signed into Game Center or Google Play Services.  

```dart
GamesServices.isSignedIn;
```  

#### Sign out  
To sign the user out of Goole Play Services. After calling, you can no longer make any actions on the user's account.  

``` dart
 GamesServices.signOut();
```  

#### Show achievements
To show the achievements screen.  
``` dart
GamesServices.showAchievements();
```  

#### Show leaderboards
To show the leaderboards screen. It takes the leaderbord id for android and iOS.  
``` dart
 GamesServices.showLeaderboards(iOSLeaderboardID: 'ios_leaderboard_id', androidLeaderboardID: 'android_leaderboard_id');
```   

#### Submit score  
To submit a ```Score``` to specific leaderboard.  
-The ```Score``` class takes three parameters:  
-```androidLeaderboardID```: the leader board id that you want to send the score for in case of android.  
-```iOSLeaderboardID``` the leader board id that you want to send the score for in case of iOS.  
-```value``` the score.  

``` dart
GamesServices.submitScore(score: Score(androidLeaderboardID: 'android_leaderboard_id',
                                       iOSLeaderboardID: 'ios_leaderboard_id',
                                       value: 5));
```  

#### Unlock achievement  
To unlock an ```Achievement```.  
The ```Achievement``` takes three parameters:  
-```androidID``` the achievement id for android.  
-```iOSID``` the achievement id for iOS.  
-```percentComplete``` the completion percent of the achievement, this parameter is optional in case of iOS.  
-```steps``` the achievement steps for Android.

``` dart
GamesServices.unlock(achievement: Achievement(androidID: 'android_id',
                                              iOSID: 'ios_id',
                                              percentComplete: 100,
                                              steps: 2)); 
```  

#### Increment (Android Only)  
To increment the steps for android achievement.

```dart
final result = await GamesServices.increment(achievement: Achievement(androidID: 'android_id', steps: 50));
print(result);
```  

#### setSteps (Android Only)
To set the steps for android achievement.

```dart
GamesServices.setSteps(achievement: Achievement(androidID: 'android_id', steps: 50));
```  

#### Show AccessPoint (iOS Only)  
To show the access point you can call the following function:  

```dart
GamesServices.showAccessPoint(AccessPointLocation.topLeading);
```  

This feature support only on the iOS, on Android there is nothing like this supported natively.  

#### Hide AccessPoint (iOS Only)  
To hide the access point.

```dart
GamesServices.hideAccessPoint();
```  

#### Player id  
To get the player you can call:

```dart
final playerID = GamesServices.getPlayerID();
```

## Installing  
Simply add the following line to your pubspec.yaml file:  
``` yaml
dependencies:
  games_services: any       # <-- Add this line
```

## Support me 🚀  

You can support this project by:  

1- Checking my [apps](https://apps.apple.com/us/developer/id928910207).  
2- Star the repo.  
3- Share the repo with your friends.  

## Follow me ❤️  

[Facebook](https://www.facebook.com/Abedalkareem.Omreyh/) | [Twitter](http://twitter.com/abedalkareemomr) | [Instagram](http://instagram.com/abedalkareemomreyh/) | [Youtube](https://www.youtube.com/user/AbedalkareemOmreyh)
