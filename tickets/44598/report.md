```
== Reproduction Report

=== Environment
- WordPress: 7.0-beta3-61849-src
- PHP: 8.3.30
- Server: nginx/1.29.5
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu
- Theme: Twenty Twenty-One (twentytwentyone)
- MU Plugins: None
- Plugins: None (first test), Hello Dolly 1.7.2 (second test)

=== Steps taken
1. Navigated to Appearance → Customize → 
   Site Identity.
2. Uploaded first logo (logo.gif - GIF image) 
   via "Select logo". Skipped cropping.
3. Confirmed logo displayed correctly in both 
   Customizer preview and frontend at 
   http://localhost:8889.
4. Navigated to Media Library and permanently 
   deleted the uploaded logo.
5. Returned to Appearance → Customize → 
   Site Identity.
6. Clicked "Change logo" and uploaded second 
   logo.gif (same filename, visually different 
   GIF image). Skipped cropping.
7. Clicked Publish in Customizer.
8. Visited frontend at http://localhost:8889 
   and performed hard refresh (Ctrl+Shift+R).
Result: ❌ Bug is not occurring

=== Expected behavior
Based on the ticket description, after permanently 
deleting the first logo and reuploading a different 
image with the same filename, the old logo should 
still appear on the frontend instead of the new one, 
even after page refresh.

=== Additional Notes
1. Tested first in a clean environment with no 
   plugins active.
2. Environment was reset and the test was repeated 
   with Hello Dolly 1.7.2 plugin active.
3. In both tests, the new logo displayed correctly 
   on the frontend immediately after publishing 
   and hard refreshing.
4. WordPress 7.0 appears to handle same-filename 
   logo replacement correctly with no caching 
   issues observed.
5. Behavior remained consistent in both scenarios 
   with no reproduction of the reported issue.

=== Screenshots/Screencast with results
[attach screenshots here]

```
