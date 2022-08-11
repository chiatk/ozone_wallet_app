
# 0.6.77+81 Hotfix

- Fixed a problem when opening a file, because of a visual error the native flutter library closed the app

# 0.6.77+80 Hotfixes

- Translation of texts.
- Support for "Open with" in Android

# 0.6.77+79 Hotfixes

- Correction of values when scanning or pasting an offer

# 0.6.77+78

- Implementation of XCH and Cat's offers, now you can create your offers, share them by any means and upload them to existing DEX's, uploading to Hashgreen and Dexie is currently enabled, more will be enabled soon.
- A button was enabled to be able to paste the offers.
- Now you can scan the offer from Dexie.
- Now Ozone is an app with which you can open .offer files on Android, it will soon be available on iOS.
- Automatic detection of the status of the offers, if the coins are spent from another wallet, the offer will be marked as cancelled.
- Performance improvements in the interface.
- Improvement of time when adding cats, now it is done in a faster way, but during the synchronization of cats it is possible to notice some lag in the interface.
- Now the synchronization or generation of wallets is no longer stopped when minimizing Ozone, this to facilitate the generation of addresses and avoid performance problems when returning to the application, if you do not want Ozone to consume resources, you must close it completely.
- Improvements when scanning active transactions, now they are only scanned every time there is a new block height, this significantly reduces the application's resource consumption.
- Improvements when calculating the addresses to receive the "change", now the address following the active one will always be used, if it does not exist, the previous one will be used, in this way, if the active wallet is m/12381/8444/ 2/20 the change address will be m/12381/8444/2/21, if it does not exist, the previous m/12381/8444/2/19 will be used
- The interface has been locked so that it only shows vertically, now if you rotate the Ozone device it will remain vertical to avoid interface crashes

# 0.6.76+77 HotFix

- First release of offers with CAT's and XCH, now you can create, accept and send offers to the different DEX configured

# 0.6.75+76 Hotfix
 
- Correction to CAT2's migration, in some devices the CAT1 tokens were not erased, now a more drastic restart is made to guarantee that migration is carried out correctly.
 
# 0.6.75+75
 
- Migration of CAT's Version 2, ChiaLisp, the program in charge of carrying out transactions of this type has been updated, in addition, changes were made in the library in charge of carrying out the transaction with CAT to support the new Standard.
- Improvements were made on the transparency screen facing this update, finally, a synchronization restart was scheduled to create the new addresses to synchronize the CAT's
- Now the corresponding derivation is shown on the receiving screen, this to be more transparent with the number of derivations used at that moment, for now there are 150 that will be increased in later versions.
- Fixed a bug that prevented the address selected to receive from being chosen, previously the configuration was lost, now the selected address is saved permanently.
- Improvements were made to improve the migration of old databases, now, if there are no derivations and it is not connected to the WebSocket, the state of the creation of said derivations will be shown so that the user is aware that it is being done a "resynchronization" process
 
# 0.6.73+73
 
- In previous updates, Catkchi was removed as the default token with the intention of improving performance at first opening, now with the use of native libraries for key derivation, this time is no longer important and has been added again as part of the commitment and thanks to the community for the support they have provided.
- Now some functions will be disabled if an internet connection is not detected, the functions are: Sending transactions and consulting Staking in Catkchi
- Universal support for old databases, many users had problems updating Ozone due to incompatible models, this made it impossible for them to re-enter the wallet, to fix this, a mechanism has now been created that restarts the "boxes" they contain incompatible models, the only box that will not change its structure and therefore will not be deleted at any time, is the "seed" box, this means that the 24 words will never be lost. In summary, if the referral list is not compatible, it will be deleted and recreated, this way we guarantee that the user can continue updating the application without fear of losing access to their data, the lost synchronization data will be recovered with the mechanisms that they already have.
 
# 0.6.71+72
 
- Changed the text displayed in the transparency header to be more descriptive.
 
# 0.6.71+71
 
- Fixed errors when changing seed.
- Changed the name of 'purchases' to 'Staking' in the Catkchi extension
- The Catkchi transparency screen was added, now you can see a list of wallets where you will find the amounts in cold, hot and to be burned that we have in our power
 - Release of resources when changing the seed or closing the app, now, when necessary, you can release resources on the server to stop synchronizing a previous wallet, this improves performance and avoids synchronization failures.
 
# 0.6.7+70
 
- Correction to database migration from version 55, which is the stable version published in the stores, adjustments were made so that it does not freeze when entering the password and finding incompatible models.
 
# 0.6.7+67
 
- Correction to fingerprint authentication on Android, in some devices fingerprint authentication failed, this was corrected by changing the theme used in the native Android environment.
- Some synchronization problems with WebSocket were corrected, now the height report is not done by blocks, if 100 addresses are at height 150, those 100 addresses are sent and processed as one, this generates a single update of performance-enhancing display.
- Fixed a visual lag on the tokens screen, this was because for each token the primary color of the token icon was calculated, now a single color is used for all.
- Fixed a visual lag that existed on the transactions screen, this was achieved by changing the loop that is responsible for processing incoming transactions, because now thanks to WebSocket synchronization, there is only one means by which new ones are registered coins, just add a listener to new coins and process them in case there are new transactions.
 
# 0.6.3+60
 
- Fixed issues with lag in the UI, changed the way the screen updates, made adjustments to only update the appropriate parts of the screen, and do fewer screen updates when not needed.
- Was implemented a native BLS library that allows better performance when making derivations, in the future it can also be used to make signatures and calculate hashes, but it remains to be seen if the performance difference is important enough to make these changes
 
# 0.6.1+58
 
- Fingerprint authentication was enabled on Android, previously it had been disabled because it failed on some devices.
 
# 0.6.0+56
 
- A new way to synchronize the wallet was added, now it is done through a WebSocket, this means that the application opens a communication with the server and simply waits for updates from the server, if there is a new block, it proceeds to update. This is very important in terms of performance, because the application does not make continuous requests to the server to synchronize, but instead sends the packet of addresses and only waits for new changes.
 
# 0.5.55+55
 
- Changed the "%" symbol to "APY" on the Staking screen
 
# 0.5.54+54
 
- Improved synchronization of the wallets, the size of addresses that is sent to synchronization by request was increased
 
# 0.5.53+53
 
- Fixed Catkchi Staking history
 
# 0.5.52+52
 
- The Catkchi extension was added, here you can make Catkchi Staking.
- Improvements were made in the synchronization of the wallet.
 
# 0.5.50+50
 
- Removed an address used in debug mode
 
# 0.5.49+49
 
- Correction in wallet synchronization, now, the synchronization is done individually, that means, there is a synchronization height for each token in each derivation
 
# 0.5.48+48
 
- Fixed the way the wallet is synchronized due to the previous method causing failures
 
# 0.5.47
 
- The address of the sender of the CAT's type transaction was corrected, in the previous version it was not done correctly
- Fixed the data displayed in outgoing transactions.
 
# 0.5.45
 
- The address of who sends a CAT's Transaction was corrected, in previous versions a mistaken value was shown
 
# 0.5.44
 
- Performance improvements when synchronizing addresses.
- Correction of small errors.
- Updated the API version, to use a new structure on the server.
- Updated the libraries to improve aspects of performance and code organization.
 
# 0.5.43
 
- Fixed a bug that deletes all previously selected tokens if the back button is pressed when the list of tokens has not yet been loaded from the server
 
# 0.5.42
 
- The possibility of auto filling the password was enabled, this to make use of third-party tools that allow password management
- Fixed confirmation message displayed when password or pin is set
- Fixed a visual bug when the password was requested.
 
# 0.5.41
 
- First public beta compiled on iOS
 
# 0.5.40
 
- First public beta
