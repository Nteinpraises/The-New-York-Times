# The New York Times Replica

A static replica of the New York Times front page, built with HTML and CSS only by a team of two. It is built mobile first and works on phone, tablet and laptop screens.

**Live site:** <https://nteinpraises.github.io/The-New-York-Times/>

## Screenshots

| Mobile (375px) | Tablet (768px) | Laptop (1440px) |

|---|---|---|
| ![Mobile view](screenshots/mobile.png) | ![Tablet view](screenshots/tablet.png) | ![Laptop view](screenshots/laptop.png) |

## Work Split

| Part | Content | Developer |

|---|---|---|
| Sections 1 to 5 | Navigation bar, top stories, right column, news stories and weather | Ntein Praises |
| Sections 6 to 11 | Videos, More News, The Athletic, Well, Latest Shows, Culture, Wirecutter, Games, site index and footer | Luther |

## Tech Stack

HTML5, CSS3 (Grid and Flexbox), Google Fonts (Libre Franklin and Source Serif 4), Google Material Icons, Git, GitHub Actions with Super-Linter.

## Responsive Design

The base styles in `style.css` are the phone layout. Two `min-width` media queries add the bigger layouts. Columns use `fr` and `minmax(0, 1fr)` instead of fixed pixels, so the page never scrolls sideways.

| Screen | Width | Layout |

|---|---|---|
| Mobile | under 768px | One column, hamburger icon, menu row scrolls inside its own box |
| Tablet | 768px and up | Two-column rows, three-column header |
| Laptop | 1024px and up | Wide main column with a narrow right column |

## How to Run

```bash
git clone https://github.com/Nteinpraises/The-New-York-Times.git
cd The-New-York-Times
```

Open `index.html` in a browser, or use the Live Server extension in VS Code. An internet connection is needed for Google Fonts and Icons.

## Testing

1. Open `index.html` and compare it with the reference page.
2. In the browser dev tools (F12), check 375px, 768px and 1440px. There must be no sideways scroll.
3. Check the console for 404 errors on images or videos.
4. Check that no conflict marker is left after a merge. This command must print nothing:

   ```bash
   grep -rn "<<<<<<<\|>>>>>>>" index.html style.css
   ```

## Challenges Faced

- **Merging two people's files.** Both of us edited the same two files, and a merge commit with conflict markers was pushed. We repaired it in a new commit instead of rewriting history.
- **Duplicate code check.** The same SVG arrow was copied 12 times in the menu. Using one icon font removed the duplicates.
- **Sideways scroll on phones.** Fixed pixel columns like `202px 378px 1fr` cannot shrink. A mobile first rewrite with `fr` and `minmax(0, 1fr)` fixed it.
- **Two layouts in one style sheet.** The two halves used different widths and needed override rules. They are now merged into one set of rules.

## What I Learned

- Grid for rows and columns, Flexbox for aligning items inside a block.
- Semantic HTML: `header`, `nav`, `main`, `section`, `article`, `figure`.
- Mobile first: write the small screen first, then add `min-width` media queries.
- Reading a linter report and resolving Git conflicts safely.

## Notes and Limits

- There is no JavaScript, so the menu, search icon and carousel arrows do not react to clicks.
- The election results are a picture, not live data.
- All ads are removed.
- Image filenames and large video files still need cleaning up.

## Authors

Ntein Praises and Luther King, Full Stack Engineers
