# Archive

A single-file, private viewer for your downloaded Instagram data, styled like the Instagram web app. Works with both the **JSON** and **HTML** export formats.

> **Unofficial.** This project is not affiliated with, endorsed by, or connected to Instagram or Meta Platforms, Inc. "Instagram" is a trademark of its owner.

> **AI-generated.** This project was written entirely by an AI assistant (Claude, made by Anthropic) from a prompt. It has not had a human code review. Read the code before trusting it with anything sensitive.

> **Status: lightly tested.** Instagram changes its export format from time to time, and this viewer has only been checked against my understanding of those formats, not a wide range of real exports. Some sections may not display correctly. Please open an issue if something looks wrong (see [Reporting problems](#reporting-problems)).

## Features

- **Home:** feed of your posts and reels, with a story bar and full-screen story viewer
- **Profile:** photo grid with tabs for Posts, Reels, Stories, Archived and Saved
- **Messages:** conversation list and chat view with photos, videos, voice notes, shared links and reactions; search within a chat
- **Activity:** followers, following, "not following you back", "you don't follow back", comments, likes, close friends, blocked, unfollowed, pending requests, hashtags
- **Search:** one search box across captions, messages, people and comments
- **Other data:** a browser for everything else in your export (searches, ads, login activity, settings…)
- Light and dark mode
- Reads JSON and HTML exports, as a folder, `.zip` file(s), or individual files

## How to use

1. **Request your data from Instagram:** Accounts Center → Your information and permissions → Export your information. Choose **JSON** or **HTML**, and include media if you want photos and videos to show.
2. Download and unzip the export (or leave it zipped).
3. Open `instagram-viewer.html` in Chrome, Edge or Firefox. No server or install needed.
4. Choose your export folder (or drop it onto the page). You can also choose `.zip` files or individual files.

No export handy? Click **Try it with sample data** to see the interface.

If your export came in several zip parts, either unzip them all into one folder, or add the zips one after another using **More → Add more files**.

## Privacy

- Your files are read and displayed **entirely inside your browser tab**. Nothing is uploaded to any server.
- The page does make two outside requests: it loads the heading font from Google Fonts, and it loads the [JSZip](https://stuk.github.io/jszip/) library from cdnjs, but only if you load a `.zip` file. If you need it to work fully offline, unzip your export and choose the folder, and self-host or remove the font link.
- The viewer is read-only. It never modifies your export files.

### Do not commit your own data

Instagram exports contain private messages, contact details and other people's information. **Never add your export to a git repository or push it to GitHub.** The included `.gitignore` blocks common export file types as a safety net, but please keep your export outside this repository entirely.

## Known limitations

- HEIC photos won't display in most browsers.
- Folder selection works best in Chrome, Edge and Firefox. Safari support is less reliable; unzip and use individual files or a zip there if needed.
- Very large exports (tens of thousands of messages or media files) can be slow and memory-hungry.
- A section only appears if the matching files are included in what you load.
- Media only displays if the photo/video files are included in your export and in the same selection.
- Instagram's export layout varies by date and account; unrecognised files appear under **More → Other data**.

## Reporting problems

Open an issue and describe which section looks wrong and which export format (JSON or HTML) you used. If you attach a sample file, **remove all personal information first** (usernames, names, message text, links, timestamps). A file with a couple of fake entries in the same structure is ideal.

## Development

It's one HTML file with inline CSS and JavaScript, with no build step and no dependencies. Edit `instagram-viewer.html` and reload.

## License

MIT. See [LICENSE](LICENSE).
