```
== Reproduction Report

=== Environment
- WordPress: 7.0-beta3-61849-src
- PHP: 8.3.30
- Server: nginx/1.29.5
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu
- Theme: Twenty Twenty-Five (twentytwentyfive)
- MU Plugins: None
- Plugins: None (first test), Hello Dolly 1.7.2 (second test)

=== Steps taken
1. Created a new page titled "Test 1". Slug was 
   auto-generated as "test-1".
2. Changed the slug from "test-1" to "test", 
   then published the page. Page is now live at 
   /test/.
3. Created a new page titled "Test 2". Slug was 
   auto-generated as "test-2".
4. Changed the slug of "Test 2" from "test-2" to 
   "test". WordPress kept "test" in the slug field 
   without immediately correcting it.
5. Clicked "Save Draft". WordPress automatically 
   corrected the slug to "test-2" upon saving.
6. Navigated to Pages list and opened "Test 1".
7. Slug on "Test 1" still showed "test" — unchanged.
8. Added content to "Test 1" and clicked Save/Update.
   Slug remained "test" after updating.
Result: ❌ Bug is not occurring

=== Expected behavior
Based on the ticket description, saving "Test 2" as 
a draft with slug "test" should have caused "Test 1's" 
slug to silently change from "test" to "test-2", 
stealing the slug from the already published page.

=== Additional Notes
1. Tested first in a clean environment with no plugins 
   active.
2. Environment was reset and the test was repeated 
   with Classic Editor 1.6.7 plugin active.
3. In WP 7.0, the slug correction now happens at save 
   time — when "test" was typed as the slug for Test 2 
   and Save Draft was clicked, WordPress correctly saved 
   it as "test-2" in the database, protecting Test 1's 
   slug throughout.
4. Behavior remained consistent in both scenarios with 
   no reproduction of the reported issue.

=== Screenshots/Screencast with results
[attach screenshots here]

```
