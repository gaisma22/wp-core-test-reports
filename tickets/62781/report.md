```
== Patch Testing Report

Patch Tested: https://github.com/WordPress/wordpress-develop/pull/8110

=== Environment
- WordPress: 7.0-beta6-62085-src
- PHP: 8.3.30
- Server: nginx/1.29.7
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu
- Theme: Twenty Twenty 3.0
- MU Plugins: None
- Plugins: None

=== Steps taken
1. Activated Twenty Twenty theme.
2. Created a new page and inserted a Calendar block.
3. Confirmed the bug - header padding and caption
   font weight differ between editor and front-end.
4. Applied patch from PR #8110
5. Hard refreshed the editor.
6. Header padding and caption font weight now
   consistent between editor and front-end.
7. Tested Typography > Appearance option - font weight updates correctly in both views.

✅ Patch is solving the problem

=== Expected result
Calendar block caption and header styling should match between editor and frontend in Twenty TwenAty.
Typography Appearance option should work in both.

=== Additional Notes
1. Bug confirmed on 7.0-beta6 before applying patch.
2. Patch applied with **`--exclude`** for
**`src/wp-content/themes/twentyten/blocks.css`** as it could not apply to that file.
Only Twenty Twenty changes were tested.
3. Four trailing whitespace warnings on apply.

=== Screenshots/Screencast with results
**Before Patch:**
- before-editor.png
- before-frontend.png

**After Patch:**
- after-editor.png
- after-frontend.png
```
