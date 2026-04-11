```
== Patch Testing Report
Patch Tested: https://github.com/WordPress/wordpress-develop/pull/9704

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
1. Created a new post using a List block with three items.
2. Published without a custom excerpt.
3. Checked the generated excerpt via the REST API at
   /wp-json/wp/v2/posts/13.
   **Before patch:** excerpt.rendered was completely empty.
   List content was not pulled into the excerpt at all.
4. Applied PR #9704 and created a new post with the same steps.
   Checked /wp-json/wp/v2/posts/15.
   **After patch:** List items appear correctly in the excerpt.

✅ Patch is solving the problem

=== Expected Result
When WordPress generates an automatic excerpt from a post using
a List block, the list item content should be included in the
generated excerpt.

=== Additional Notes
1. Bug confirmed on WordPress 7.0-beta6. List block content was
   completely ignored when generating automatic excerpts.

=== Screenshots/Screencast with results
**Before Patch:**
- before-excerpt.png

**After Patch:**
- after-excerpt.png
```
