```
== Reproduction Report

=== Environment
- WordPress: 7.0-beta3-61849-src
- PHP: 8.3.30
- Server: nginx/1.29.5
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu
- Theme: Twenty Twenty (twentytwenty)
- MU Plugins: None
- Plugins: None (first test), Hello Dolly 1.7.2 (second test)

=== Steps taken
1. Activated Twenty Twenty theme.
2. Created a new page titled "Image Alignment Test".
3. Added a paragraph block with dummy text.
4. Added an image block and uploaded an image.
5. Aligned the image block to the right.
6. Resized the image by dragging the corner handle inward. Final width: 117px.
7. Confirmed text wrapped around the right-aligned image in the editor.
8. Published the page and visited the frontend.
9. Compared editor vs frontend. Image size and alignment were consistent in both views.
10. Inspected the page source and searched for the CSS rule reported as the root cause:
    .entry-content > .alignleft, .entry-content > .alignright { position: absolute; }
    It was not present anywhere in the stylesheet.
Result: ❌ Bug is not occurring

=== Expected behavior
Based on the ticket, aligning an image block to the right and resizing it should produce inconsistent results between the editor and frontend. The image size should not be respected and the alignment should differ between views. The root cause was a position: absolute rule applied to .alignleft and .alignright inside .entry-content in Twenty Twenty's stylesheet.

=== Additional Notes
1. Tested first in a clean environment with no plugins active.
2. Environment was reset and the test was repeated with Hello Dolly 1.7.2 active.
3. The CSS rule identified as the root cause in the original report is gone from the current version of Twenty Twenty. It was present in Twenty Twenty 1.9 and has since been removed.
4. Both tests produced the same result. No reproduction in either scenario.
5. Removing needs-testing. Adding close as the bug no longer reproduces in WP 7.0.
   Leaving open in case someone wants to run a second test.

=== Screenshots/Screencast with results
- 01-editor-image-aligned-right.png
- 02-frontend-image-aligned-right.png

```
