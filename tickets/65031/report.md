```
== Patch Testing Report
Patch Tested: https://github.com/WordPress/wordpress-develop/pull/11463

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
1. Went to Users > Edit User and clicked Set New Password.
   **Before patch:** Eye icon sits lower than the Hide text.
2. Applied PR #11463 and hard refreshed.
   **After patch:** Eye icon aligned with Hide text.

✅ Patch is solving the problem

=== Expected Result
The password toggle button eye icon should sit at the same
vertical level as the Hide text on the user edit screen.

=== Additional Notes
1. Bug confirmed on WordPress 7.0-beta6. The eye icon on the
   password toggle button on user-edit.php sits lower than
   the Hide text before the patch.
2. After the patch the alignment is correct.

=== Screenshots/Screencast with results
**Before Patch:**
- before-user-edit.png

**After Patch:**
- after-user-edit.png
```
