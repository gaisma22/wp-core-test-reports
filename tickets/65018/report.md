```
== Patch Testing Report
Patch Tested: https://github.com/WordPress/wordpress-develop/pull/11437

=== Environment
- WordPress: 7.0-beta6-62085-src
- PHP: 8.3.30
- Server: nginx/1.29.7
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu 24.04
- Theme: Twenty Twenty-Five 1.4
- MU Plugins: None
- Plugins: Classic Editor

=== Steps Taken
1. Went to Posts > Add New on the classic editor screen.
2. Observed the layout below the page heading.
   **Before patch:** Content area overflows its container,
   visible as a red line on the left edge.
3. Applied PR #11437 and hard refreshed.
   **After patch:** Red line gone. Layout looks correct.

✅ Patch is solving the problem

=== Expected Result
The post edit screen content area should sit within
its container with no horizontal overflow.

=== Additional Notes
1. Bug confirmed on WordPress 7.0-beta6 on the classic
   post edit screen.
2. Classic Editor plugin was required to reproduce the issue
   since the block editor does not show the same layout.

=== Screenshots/Screencast with results
**Before Patch:**
- before-overflow.png

**After Patch:**
- after-overflow.png
```
