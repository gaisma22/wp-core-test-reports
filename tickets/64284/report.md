```
== Reproduction Report

=== Environment
- WordPress: 7.0-beta6-62085-src
- PHP: 8.3.30
- Server: nginx/1.29.6
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu
- Theme: Twenty Twenty-Five 1.4
- MU Plugins: None
- Plugins: None (first test), Hello Dolly 1.7.2 (second test)

=== Steps taken
1. Navigated to Posts -> Add New Post.
2. Entered "2×2 Test Post" as the post title using the
   multiplication symbol x (U+00D7).
3. Published the post.
4. Checked the permalink and slug field after publishing.
5. Slug shows "2x2-test-post" - x correctly converted to "x".
6. Reset environment and repeated with Hello Dolly 1.7.2 active.
7. Same result - slug shows "2x2-test-post".
Result: ❌ Bug is not occurring

=== Expected behavior
Based on the ticket, the multiplication symbol x (U+00D7) in a post
title should be stripped from the slug, producing "22-test-post"
instead of "2x2-test-post".

=== Additional Notes
1. Tested first in a clean environment with no plugins active.
2. Environment was reset and the test was repeated with Hello
   Dolly 1.7.2 active.
3. Both tests produced the same result.
4. This matches comment #16 by @ozgursar who could not reproduce
   on 7.0-beta2. The fix may have been applied as part of #19820.
5. Removing `needs-testing` as the bug does not reproduce in WordPress
   7.0-beta6-62085-src. Adding `close`.

=== Screenshots/Screencast with results
- [screenshots]
```
