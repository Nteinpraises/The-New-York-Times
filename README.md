# The New York Times Replica

This is a static replica of the New York Times front page, built with HTML and CSS only by a team of two. It copies the layout of the real page, from the navigation bar and the top stories to the news sections, the opinion and arts columns and the footer.

## Problem

A news front page looks simple, but it is a hard layout exercise. It mixes a header, a bordered top story box, columns of different widths, photo and text pairs, small lists and long rows of sections on one page. It also has to be built by two people who write into the same `index.html` and `style.css` without breaking each other's work.

## Project Goals

- Rebuild the front page section by section, from the navigation bar to the footer.
- Use semantic HTML and CSS Grid and Flexbox for every layout.
- Keep one `index.html` and one `style.css` that both developers can edit.
- Pass the repository linter, including the duplicate code check.
- Follow a clean Git workflow: personal branches, a team branch and pull requests.

## Work Split

| Sections 1 to 5 | Navigation bar, top stories, right column (Opinion and Most Shared), election results image, Middle East, aviation, pope, Snoopy, Big Bear and weather | Ntein Praises |
| Sections 6 to 11 | Watch Today's Videos, More News, The Athletic, Well, Latest Shows, Culture and Lifestyle, Wirecutter, Games, the site index (News, Opinion, Arts, Living) and the footer | Luther |

## Tech Stack

- Language: HTML5 and CSS3
- Layout: CSS Grid and Flexbox
- Fonts: Google Fonts (Libre Franklin and Source Serif 4)
- Tools: Git, GitHub, GitHub Actions with Super-Linter, VS Code with Live Server

## Features

- Navigation bar with a search icon, the date, the language links, the logo and a log in button.
- Menu row with 12 sections and a double line underneath, with the arrows drawn in CSS.
- "Free to read" top box with an autoplaying video and a right column with the featured story, two cards, Opinion and Most Shared.
- Story blocks built with `article`, `figure` and `figcaption`.
- Election results shown as an image, and a static weather block.
- Video row, More News, The Athletic, Well, Latest Shows, Culture, Wirecutter, Games and a full site index.
- Footer with the link columns and the account links.

## How to Run

```bash
git clone https://github.com/Nteinpraises/The-New-York-Times.git
cd The-New-York-Times
```

Open `index.html` in a browser, or start it with the Live Server extension in VS Code.

## Testing

1. Open `index.html` at a desktop width and compare it with the reference page, section by section.
2. Reset the browser zoom with `Ctrl+0` before judging sizes.
3. Open the browser console (F12) and check that no image or video returns a 404 error.
4. Check that no conflict marker is left after a merge:

## Challenges Faced

- **A grid that did nothing.** The nav bar used `grid-template-columns` with brackets around the values on a `display: flex` element. Switching to `display: grid` with `1fr 2fr 1fr` fixed it.
- **An invalid closing tag.** `</div class="video-div">` is not valid HTML and left a story without its wrapper.
- **The duplicate code check.** The linter failed because the same SVG arrow was copied 12 times in the menu. Drawing the arrow with a CSS `::after` removed the duplicates.
- **A page cut into pieces.** The reference is a PDF split into pages, so some stories were cut at a page break and had to be rebuilt as one block.
- **Merging two people's files.** Both developers wrote the same two files, so Git reported conflicts on all of `index.html` and `style.css`. A merge commit was pushed with the conflict markers still inside, and it had to be repaired in a new commit instead of rewriting history.
- **Two layouts in one stylesheet.** The second half used a 908px wrapper and a video row with fixed pixel columns, while the first half used a 1200px page. Two override rules made both halves the same width.

## What I Learned

- Choosing between Grid and Flexbox: Grid for rows and columns, Flexbox for aligning items inside a block.
- Writing semantic HTML with `header`, `nav`, `main`, `section`, `article`, `figure` and `figcaption`.
- Reading a linter report and finding the real cause of an error.
- Drawing small icons with CSS pseudo-elements instead of repeating SVG code.
- Using `git fetch`, `git merge`, `git reset` and a backup branch to resolve conflicts safely.
- Finding clashing CSS rules with the browser inspector.

## Notes and Limits

- The layout is built for desktop screens.
- There is no JavaScript, so the menu, the search icon and the carousel arrows do not react to clicks.
- The election results are a picture, not live data.
- The second half of the page includes the advertisement banners, which the first half leaves out.

## Authors

Ntein Praises and Luther King, Full Stack Engineers
