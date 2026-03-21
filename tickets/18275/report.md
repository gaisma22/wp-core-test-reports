```
== Reproduction Report

=== Environment
- WordPress: 7.0-beta1-61709-src
- PHP: 8.2.29
- Server: nginx/1.29.5
- Database: MySQL 8.4.8
- Browser: Firefox
- OS: Ubuntu
- Theme: Twenty Twenty-Five (twentytwentyfive)
- MU Plugins: None
- Plugins: None (first test), Classic Editor 1.6.7 (second test)


=== Steps taken
1. Uploaded an image to the Media Library (original size: 2400 × 1350).
2. Navigated to Media → Selected the image → Clicked “Edit Image”.
3. Performed a manual random crop using the crop tool.
4. Clicked “Apply Crop” and then “Save Edits”.
5. Returned to the Media Library (Grid View) to observe the thumbnail preview and image behavior.
6. Repeated the exact same steps after activating the Classic Editor plugin.
Result: ❌ Bug is not occurring


=== Expected behavior
- After cropping and saving edits, the Media Library thumbnail and edited image should reflect the crop correctly without visual issues or incorrect preview behavior as described in the ticket.

=== Additional Notes
1. Tested first in a clean environment with no plugins active.
2. Environment was reset and the test was repeated with Classic Editor plugin active.
3. Behavior remained consistent in both scenarios with no reproduction of the reported issue.

=== Screenshots/Screencast with results
- Screenshots provided showing the crop process, saved edits, and Media Library thumbnail behavior with and without plugin active.

```
