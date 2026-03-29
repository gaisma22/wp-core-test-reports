```
== Reproduction Report

=== Environment
- WordPress: 7.0-beta6-62085-src
- PHP: 8.3.30
- Server: nginx/1.29.7
- Database: MySQL 8.4.8
- Browser: Brave
- OS: Ubuntu
- Theme: Twenty Twenty-Five 1.4
- MU Plugins: None
- Plugins: None (first test), Classic Editor 1.6.7 (second test)

=== Steps taken
1. Created a new page and added an Audio block.
2. Clicked Insert from URL and pasted a OneDrive
   public share URL (302 redirect to an audio file).
3. Audio player appeared but showed **`0:00 / 0:00`** -
   no duration, controls do nothing.
4. Published the page and checked the frontend.
   Same result.
5. Reset environment. Activated Classic Editor.
6. Created a new page. Clicked Add Media >
   Insert from URL with the same OneDrive URL.
   Rendered as a plain HTML link, no player.
7. Switched to Text/Code view and inserted:
   **`[audio src="onedrive-url"]`**
   Frontend showed the URL as a plain link, no player.
🐞 Bug is occurring

=== Expected behavior
A OneDrive public share URL (302 redirect) should load and play correctly in the WordPress audio player in both the block editor and Classic Editor.

=== Additional Notes
1. Right-clicking the audio block and opening the URL
   directly in a new tab confirms the OneDrive URL is
   valid and accessible - the player just can't
   resolve the redirect.
2. Behavior consistent with comment #2 by @desrosj.
   Bug still reproduces on 7.0-beta6.


=== Screenshots/Screencast with results

**Block Editor:**

- 01-block-editor.png
- 02-block-frontend.png

**Classic Editor:**

- 03-classic-editor.png
- 04-classic-frontend.png
```
