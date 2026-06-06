Format a blog post by scraping its original Wix page and updating the local markdown file to match.

Usage: /format-blog-post <wix-url>

## Steps

Given the Wix URL `$ARGUMENTS`, do the following:

### 1. Scrape the Wix post

Fetch `$ARGUMENTS` twice in parallel:
- **Pass 1** — extract the complete post body in reading order: every paragraph word-for-word, all headings with their level (H2/H3), all bold/italic spans, all blockquotes or pull quotes, and all hyperlinks (anchor text + href).
- **Pass 2** — extract every image in the post body: its src URL, any caption, where it appears (after which paragraph/heading), and — critically — whether multiple images appear **side-by-side / in a gallery** or **stacked individually**. Note the layout explicitly.

### 2. Find the local markdown file

The blog posts live in `src/content/blog/*.md`. Match the post by title (from the `title:` frontmatter field). Read the current file content.

### 3. Check available images

List the contents of `public/images/blog/{slug}/` to see which images are already copied there.
Also list `~/Desktop/blog resources/{folder}/` (the folder name matches the post title, check CLAUDE.md for the 3 exceptions). Note any images that are referenced on the Wix page but not yet in the public folder.

### 4. Copy missing images

For any image needed that isn't already in `public/images/blog/{slug}/`, copy it from `~/Desktop/blog resources/{folder}/` using a descriptive filename (kebab-case, preserve extension). The hero image is typically already there as `hero.{ext}` — don't duplicate it unless it also appears inline.

### 5. Rewrite the markdown file

Produce the complete updated markdown file:

**Frontmatter** — keep all existing fields unchanged (title, date, description, heroImage, url, draft).

**Body** — rewrite to match the Wix structure exactly:
- *Italic* for italic text, **bold** for bold text
- `> blockquote` for pull quotes
- `## Heading` / `### Sub-heading` matching Wix H2/H3 levels
- `[anchor text](url)` for all hyperlinks found in the body
- Single image: `![descriptive alt text](/images/blog/{slug}/filename.ext)`
- **Multiple images displayed side-by-side or in a gallery on Wix:**
  ```html
  <div class="image-gallery">
    <img src="/images/blog/{slug}/image1.ext" alt="..." />
    <img src="/images/blog/{slug}/image2.ext" alt="..." />
  </div>
  ```
- **Multiple images stacked vertically on Wix:** use separate `![]()` lines

Preserve all paragraph text word-for-word. Do not invent or summarise content.

### 6. Build and commit

```bash
npm run build
git add src/content/blog/{slug}.md public/images/blog/{slug}/
git commit -m "Format '{title}' post from Wix original"
git push
```

### Notes

- The hero image (`heroImage` in frontmatter) is used for the blog listing card only — it does not appear at the top of the post page. Do not insert it as the first inline image unless it genuinely appears in the body of the Wix post.
- Image paths in markdown must start with `/images/blog/...` (absolute from site root, base is `/`).
- The three posts that share image folders: "Part 2: p5.js on the move" uses "Part 1: p5.js adventures" folder, "How to make a Saturn chart?" uses "Wild at heart and weird on top" folder, "The Barbie Safary" uses "Girls can be anything" folder.
