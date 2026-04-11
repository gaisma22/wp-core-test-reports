```
== Patch Testing Report
Patch Tested: https://github.com/WordPress/wordpress-develop/pull/11352

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
1. Created a new post using a Verse block with three lines
   separated by Enter.
2. Published without a custom excerpt.
3. Checked the generated excerpt via the REST API at
   /wp-json/wp/v2/posts/6.
   **Before patch:** Words from adjacent lines were stuck together
   with no spaces. e.g. "this is line onethis is line two"
4. Applied PR #11352 and created a new post with the same steps.
   Checked /wp-json/wp/v2/posts/9.
   **After patch:** Words are correctly separated by spaces.
   e.g. "this is line one this is line two this is line three"

✅ Patch is solving the problem

=== Expected Result
When WordPress generates an automatic excerpt from a post using
a Verse block, words from adjacent lines should be separated
by spaces.

=== Additional Notes
1. Bug confirmed on WordPress 7.0-beta6. The br tags in Verse
   block content were stripped without preserving word boundaries,
   causing words from adjacent lines to concatenate in the
   generated excerpt.

=== Screenshots/Screencast with results
**Before Patch:**
- before-excerpt.png

**After Patch:**
- after-excerpt.png
```
