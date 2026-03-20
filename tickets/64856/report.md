```
== Patch Testing Report

Patch Tested: https://github.com/WordPress/wordpress-develop/pull/11282

=== Environment
- WordPress: 7.0-beta5-61991-src
- PHP: 8.3.30
- Server: nginx/1.29.5
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu
- Theme: Twenty Twenty-Five 1.4
- MU Plugins: None
- Plugins: WP Button Variations Checker 1.1.0

=== Steps taken
1. Applied patch from PR #11282 using git apply
2. Rebuilt CSS using npm run build:dev
3. Navigated to the WP Button Variations Checker plugin page
4. Observed the Secondary button rows - active state is now
   clearly different from the default state
5. Navigated to Settings -> Permalinks
6. Clicked the **`%hour%`** structure tag
7. The active tag now has a visible background and inset shadow
✅ Patch is solving the problem

=== Expected result
Secondary variation buttons and structure tags on the Permalinks
page should have a pressed/active state that is easy to tell
apart from the default state.

=== Additional Notes
- Tested with the Default (purple) admin color scheme from the
  WP 7.0 admin reskin
- The patch raises the active state background opacity from 0.04
  to 0.15 and adds an inset box-shadow - the pressed state is
  now clearly visible
- Button group active states also show improved distinction
- WP Button Variations Checker plugin used for testing: https://github.com/t-hamano/wp-button-variations-checker

=== Screenshots/Screencast with results

Before patch:
- 01-before-button-variations.png
- 02-before-permalinks.png

After patch:
- 01-after-button-variations.png
- 02-after-permalinks.png

```
