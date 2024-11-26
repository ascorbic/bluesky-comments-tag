# Bluesky Comments Tag

A lightweight, customizable web component for using Bluesky comment for your website comments. The component lazy loads comments when they enter the viewport and supports extensive styling customization.

## Features

- ⚡ Lightweight with no framework or dependencies
- 🌐 Use directly in HTML - no bundler or installer needed
- 🔒 Isolated styles with Shadow DOM
- 🎨 Highly customizable with CSS variables and Shadow Parts
- 🎯 Lazy loading - only loads comments when visible

## Usage

You can load the component from a CDN and then use it directly:

```html
<!-- Use the element -->
<bluesky-comments url="https://bsky.app/profile/mk.gg/post/3lb3cxyeh3c2f">
</bluesky-comments>
<!-- Include the script tag anywhere -->
<script type="module">
  import "https://esm.sh/bluesky-comments-tag/load";
</script>
```

## Styling

The component can be customized in two ways:

1. Using CSS Custom Properties (variables)
2. Using Shadow Parts for direct styling of internal elements

### Basic Styling Example

```css
bluesky-comments {
  /* Colors */
  --bluesky-text-color: #333;
  --bluesky-handle-color: #888;
  --bluesky-footer-text-color: rgb(111, 134, 159);
  --bluesky-bg-color: #fff;
  --bluesky-hover-bg: #f0f0f0;
  --bluesky-border-color: #e0e0e0;

  /* Typography */
  --bluesky-font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  --bluesky-font-size: 14px;
  --bluesky-footer-font-size: 14px;
}
```

### Dark Mode Support

```css
@media (prefers-color-scheme: dark) {
  bluesky-comments {
    --bluesky-bg-color: #1e293b;
    --bluesky-text-color: #e2e8f0;
    --bluesky-border-color: #4a5568;
    --bluesky-hover-bg: #2d3748;
    --bluesky-handle-color: #9ca3af;
    --bluesky-footer-text-color: #9ca3af;
  }
}
```

### Using Shadow Parts

The component exposes several parts that can be styled directly using the `::part()` selector:

```css
bluesky-comments::part(avatar) {
  border: 2px solid gold;
}

bluesky-comments::part(comment-header) {
  background: #f8f9fa;
}

bluesky-comments::part(comment-body) {
  font-size: 1.1em;
}

bluesky-comments::part(comment-content) {
  line-height: 1.6;
}

bluesky-comments::part(comment-footer) {
  padding: 8px 12px;
}
```

Available parts:

- `avatar` - The user's avatar image or default avatar
- `comment-header` - The header section containing avatar and user info
- `comment-body` - The main comment content container
- `comment-content` - The text content of the comment
- `comment-footer` - The footer with interaction counts

### All Available CSS Custom Properties

| Property                     | Default             | Description               |
| ---------------------------- | ------------------- | ------------------------- |
| --bluesky-font-family        | -apple-system, etc. | Font family for all text  |
| --bluesky-font-size          | 14px                | Base font size            |
| --bluesky-text-color         | #333                | Main text color           |
| --bluesky-handle-color       | #888                | Username/handle color     |
| --bluesky-footer-text-color  | rgb(111, 134, 159)  | Footer text color         |
| --bluesky-bg-color           | #fff                | Background color          |
| --bluesky-hover-bg           | #f0f0f0             | Hover state background    |
| --bluesky-border-color       | #e0e0e0             | Border color              |
| --bluesky-spacing-xs         | 5px                 | Extra small spacing       |
| --bluesky-spacing-sm         | 8px                 | Small spacing             |
| --bluesky-spacing-md         | 10px                | Medium spacing            |
| --bluesky-avatar-size        | 24px                | Size of avatar images     |
| --bluesky-avatar-bg          | #e0e0e0             | Default avatar background |
| --bluesky-reply-border-width | 2px                 | Reply border width        |
| --bluesky-footer-font-size   | 14px                | Footer text size          |
| --bluesky-icon-size          | 18px                | Size of footer icons      |

## Theme Examples

Take these with a pinch of salt: Claude made them up. You can use these as a starting point for your own custom themes.

### Modern Blog Theme

```css
bluesky-comments {
  --bluesky-bg-color: #ffffff;
  --bluesky-font-family: "Inter", system-ui, sans-serif;
  --bluesky-font-size: 15px;
  --bluesky-text-color: #1a2b3c;
  --bluesky-handle-color: #64748b;
  --bluesky-footer-text-color: #94a3b8;
  --bluesky-border-color: #e2e8f0;
  --bluesky-hover-bg: #f8fafc;
  --bluesky-spacing-xs: 8px;
  --bluesky-spacing-sm: 12px;
  --bluesky-spacing-md: 16px;
  --bluesky-avatar-size: 40px;
  --bluesky-avatar-bg: #f1f5f9;
  --bluesky-reply-border-width: 2px;
  --bluesky-footer-font-size: 13px;
  --bluesky-icon-size: 16px;
}

/* Optional: Enhanced styling using parts */
bluesky-comments::part(avatar) {
  border: 2px solid #fff;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}

bluesky-comments::part(comment-content) {
  line-height: 1.6;
}
```

### Clean Documentation Theme

```css
bluesky-comments {
  --bluesky-bg-color: #fcfcfc;
  --bluesky-font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    sans-serif;
  --bluesky-font-size: 14px;
  --bluesky-text-color: #2c3e50;
  --bluesky-handle-color: #718096;
  --bluesky-footer-text-color: #a0aec0;
  --bluesky-border-color: #edf2f7;
  --bluesky-hover-bg: #f7fafc;
  --bluesky-spacing-xs: 6px;
  --bluesky-spacing-sm: 10px;
  --bluesky-spacing-md: 12px;
  --bluesky-avatar-size: 32px;
  --bluesky-avatar-bg: #edf2f7;
  --bluesky-reply-border-width: 1px;
  --bluesky-footer-font-size: 12px;
  --bluesky-icon-size: 14px;
}

bluesky-comments::part(comment-header) {
  padding: 8px 12px;
  background: #f8fafc;
  border-radius: 4px 4px 0 0;
}
```

### Dark Theme

```css
bluesky-comments {
  --bluesky-bg-color: #1e1e2e;
  --bluesky-font-family: system-ui, sans-serif;
  --bluesky-font-size: 14px;
  --bluesky-text-color: #cdd6f4;
  --bluesky-handle-color: #a6adc8;
  --bluesky-footer-text-color: #7f849c;
  --bluesky-border-color: #313244;
  --bluesky-hover-bg: #181825;
  --bluesky-spacing-xs: 6px;
  --bluesky-spacing-sm: 10px;
  --bluesky-spacing-md: 14px;
  --bluesky-avatar-size: 36px;
  --bluesky-avatar-bg: #313244;
  --bluesky-reply-border-width: 1px;
  --bluesky-footer-font-size: 13px;
  --bluesky-icon-size: 16px;
}

bluesky-comments::part(comment-header) {
  background: rgba(49, 50, 68, 0.5);
}

bluesky-comments::part(avatar) {
  border: 1px solid #45475a;
}
```

### Minimal Reddit-Style Theme

```css
bluesky-comments {
  --bluesky-bg-color: #ffffff;
  --bluesky-font-family: Verdana, arial, helvetica, sans-serif;
  --bluesky-font-size: 13px;
  --bluesky-text-color: #1c1c1c;
  --bluesky-handle-color: #787c7e;
  --bluesky-footer-text-color: #787c7e;
  --bluesky-border-color: #edeff1;
  --bluesky-hover-bg: #f6f7f8;
  --bluesky-spacing-xs: 4px;
  --bluesky-spacing-sm: 6px;
  --bluesky-spacing-md: 8px;
  --bluesky-avatar-size: 24px;
  --bluesky-avatar-bg: #edeff1;
  --bluesky-reply-border-width: 2px;
  --bluesky-footer-font-size: 12px;
  --bluesky-icon-size: 16px;
}

bluesky-comments::part(comment-content) {
  line-height: 1.5;
  padding: 4px 0;
}

bluesky-comments::part(comment-footer) {
  opacity: 0.8;
}
```

### Magazine Style Theme

```css
bluesky-comments {
  --bluesky-bg-color: #fffef9;
  --bluesky-font-family: Georgia, "Times New Roman", serif;
  --bluesky-font-size: 16px;
  --bluesky-text-color: #2d3436;
  --bluesky-handle-color: #636e72;
  --bluesky-footer-text-color: #b2bec3;
  --bluesky-border-color: #dfe6e9;
  --bluesky-hover-bg: #f5f6fa;
  --bluesky-spacing-xs: 8px;
  --bluesky-spacing-sm: 12px;
  --bluesky-spacing-md: 20px;
  --bluesky-avatar-size: 48px;
  --bluesky-avatar-bg: #dfe6e9;
  --bluesky-reply-border-width: 1px;
  --bluesky-footer-font-size: 14px;
  --bluesky-icon-size: 18px;
}

bluesky-comments::part(comment-content) {
  line-height: 1.7;
  letter-spacing: 0.2px;
}

bluesky-comments::part(avatar) {
  border-radius: 8px;
}
```

## Browser Support

The component uses standard web components and modern JavaScript features.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use this component in your projects.
