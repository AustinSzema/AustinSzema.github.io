# Austin Szema's Blog

A simple, scalable static blog system with a clean, modern design.

## File Structure

```
blog/
├── index.html              # Main blog listing page
├── style.css               # Shared styles for all pages
├── blog.js                 # JavaScript to load posts on index
├── posts.json              # Blog post metadata database
├── game-designer-meaning.html  # Individual blog post
├── player-agency.html          # Individual blog post
└── README.md               # This file
```

## How to Add a New Blog Post

### Method 1: Manual (Recommended for learning)

1. **Create the HTML file**
   - Copy an existing post file (e.g., `player-agency.html`)
   - Rename it with a descriptive slug (e.g., `my-new-post.html`)
   - Update the content:
     - Change the `<title>` tag
     - Update the `<h1>` (post title)
     - Update the `<h2>` (author name)
     - Update the `<h3>` (date)
     - Replace paragraph content with your post

2. **Update posts.json**
   - Add a new entry at the TOP of the array (newest posts first)
   - Fill in all fields:
     ```json
     {
       "id": "unique-post-id",
       "title": "Your Post Title",
       "author": "Austin Szema",
       "date": "2026-02-15",
       "excerpt": "A brief summary of the post (1-2 sentences)",
       "filename": "my-new-post.html"
     }
     ```

3. **Test**
   - Open `index.html` in a browser
   - Your new post should appear at the top
   - Click to make sure it links correctly

### Method 2: Using the Template Generator (Optional)

You can create a simple Node.js script to generate new posts:

```bash
node new-post.js "My Post Title" "This is the excerpt"
```

## Post Template

Here's the basic structure for a new post:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Your Title - Austin Szema</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Host+Grotesk:ital,wght@0,300..800;1,300..800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <a href="index.html" class="back-link">Back to all posts</a>
        
        <article>
            <h1>Your Post Title</h1>
            <h2>Austin Szema</h2>
            <h3>Month Day, Year</h3>
            
            <p>Your first paragraph...</p>

            <p>Your second paragraph...</p>
            
            <!-- Add more paragraphs as needed -->
        </article>
    </div>
</body>
</html>
```

## Customization

### Changing Colors
Edit the CSS variables in `style.css`:
```css
:root {
  --bg-dark: #020617;
  --blue-light: #60a5fa;
  /* ... etc */
}
```

### Changing Fonts
Update the Google Fonts link in the `<head>` section and change the `font-family` in CSS.

### Adding Images
Simply add `<img>` tags in your article:
```html
<img src="image.jpg" alt="Description">
```

## Deployment

This is a static site, so you can deploy it anywhere:
- **GitHub Pages**: Push to a repo and enable GitHub Pages
- **Netlify**: Drag and drop the folder
- **Vercel**: Import the repo
- **Any web host**: Upload via FTP

## Future Enhancements

Consider adding:
- Tags/categories for posts
- Search functionality
- RSS feed
- Dark/light mode toggle
- Reading time estimates
- Social sharing buttons
- Comments (via Disqus or similar)
