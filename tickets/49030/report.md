```
== Patch Testing Report

Patch Tested: https://core.trac.wordpress.org/attachment/ticket/49030/49030.diff

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
1. Added a Custom HTML widget to footer containing
   a YouTube iframe with width set to **`560px`**.
2. Visited the frontend and checked the iframe width
   via browser console:
   **`document.querySelector('.widget iframe').style.width`**
   Result before patch: **`570px`**
3. Applied patch from ticket #49030.
4. Hard refreshed the frontend and ran the same
   console command.
   Result after patch: **`''`**

✅ Patch is solving the problem

=== Expected result
Twenty Twenty's Intrinsic Ratio Embeds resize function should only target iframes and videos
inside post content, not elements in widgets or other areas outside the post content.

=== Additional Notes
1. Bug confirmed on WordPress 7.0-beta6 - the resize
   function was changing the footer widget iframe
   width from **`560px`** to **`570px`**.
2. After the patch, the footer widget iframe width
   is no longer modified by the theme JavaScript.
3. Original patch path was missing the `src/` prefix.
   Applied after fixing with **`sed`**.

=== Screenshots/Screencast with results
**Before Patch:**
- before-frontend-footer.png
- before-console.png

**After patch:**
- after-console.png
```
