```
== Patch Testing Report
Patch Tested: https://github.com/WordPress/wordpress-develop/pull/11354

=== Environment
- WordPress: 7.0-beta6-62085-src
- PHP: 8.3.30
- Server: nginx/1.29.7
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu 24.04
- Theme: Twenty Twenty-Five 1.4
- MU Plugins: None
- Plugins: None

=== Steps Taken
1. Went to Users > Profile and set color scheme to Sunrise.
2. Visited the frontend.
   **Before patch:** Toolbar showed default black colors.
3. Applied PR #11354 and hard refreshed.
   **After patch:** Toolbar matched Sunrise colors.
4. Switched to Ectoplasm, saved, hard refreshed.
   **After patch:** Toolbar matched Ectoplasm colors.

✅ Patch is solving the problem

=== Expected Result
The frontend admin toolbar should match the color scheme selected
in the user profile.

=== Additional Notes
1. On 7.0-beta6 without the patch, the toolbar stays black on the
   frontend no matter what color scheme is set in the admin.
2. Tested Sunrise and Ectoplasm. Both worked after the patch.

=== Screenshots/Screencast with results
**Before Patch:**
- before-sunrise.png

**After Patch:**
- after-sunrise.png
- after-ectoplasm.png
```
