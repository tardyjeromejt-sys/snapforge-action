# SnapForge Action

Generate OG images, QR codes, PDFs, placeholders, and more in your GitHub Actions workflow using the [SnapForge API](https://usesnapforge.com).

## Features

- **OG Images** — 10 templates (blog, product, social, event, article, github, minimal, gradient, stats, announcement)
- **QR Codes** — Custom colors, sizes, and error correction
- **PDFs** — From templates or custom HTML
- **Placeholders** — SVG placeholders with custom dimensions and colors
- **Resize** — Resize images by URL
- **Metadata** — Extract Open Graph metadata from any URL

## Quick Start

```yaml
- name: Generate OG image
  uses: tardyjeromejt-sys/snapforge-action@v1
  with:
    type: og
    template: blog
    title: 'My Blog Post'
    theme: dark
```

## Usage Examples

### Generate a QR Code

```yaml
- name: Generate QR code
  uses: tardyjeromejt-sys/snapforge-action@v1
  with:
    type: qr
    text: 'https://usesnapforge.com'
    fg-color: '6366F1'
    bg-color: 'ffffff'
```

### Generate a Placeholder

```yaml
- name: Generate placeholder
  uses: tardyjeromejt-sys/snapforge-action@v1
  with:
    type: placeholder
    width: '800'
    height: '400'
    bg-color: '6366F1'
    fg-color: 'ffffff'
```

### Extract Metadata

```yaml
- name: Extract metadata
  uses: tardyjeromejt-sys/snapforge-action@v1
  with:
    type: metadata
    url: 'https://github.com'
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `type` | Asset type: og, qr, pdf, placeholder, resize, metadata | Yes | — |
| `api-key` | SnapForge API key (for PDF generation) | No | — |
| `template` | OG image template name | No | blog |
| `title` | Title for OG images | No | Hello World |
| `theme` | OG theme (light/dark) | No | light |
| `text` | Text/URL for QR codes | No | — |
| `url` | URL for metadata/resize | No | — |
| `width` | Width for placeholder/resize | No | 600 |
| `height` | Height for placeholder/resize | No | 400 |
| `bg-color` | Background color (hex) | No | cccccc |
| `fg-color` | Foreground color (hex) | No | 666666 |
| `output-path` | Output directory | No | ./snapforge-output |

## Outputs

| Output | Description |
|--------|-------------|
| `url` | Direct URL to the generated asset |
| `file-path` | Local path to the downloaded file |

## Links

- [SnapForge Website](https://usesnapforge.com)
- [API Documentation](https://usesnapforge.com/docs)
- [Playground](https://usesnapforge.com/playground)
- [npm Package](https://www.npmjs.com/package/@jeninho/snapforge)

## License

MIT
