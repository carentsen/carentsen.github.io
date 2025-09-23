# Content Creation Instructions

## Blog Posts

### File Naming Convention
- **Format**: `YYYY-MM-DD-title-with-hyphens.markdown`
- **Location**: `_posts/` directory
- **Example**: `2025-09-23-my-new-blog-post.markdown`

### Front Matter Template
```yaml
---
layout: post
title: "Your Post Title"
date: 2025-09-23 12:00:00 +0000
categories: [category1, category2]
tags: [tag1, tag2, tag3]
excerpt: "Brief description for social sharing and previews"
author: "Christian Arentsen"
---
```

### Content Structure
1. **Opening Hook** - Engaging first paragraph
2. **Main Content** - Well-structured sections with headers
3. **Conclusion** - Clear takeaways or call-to-action
4. **Code Blocks** - Use triple backticks with language specification

### Best Practices
- Use descriptive, SEO-friendly titles
- Include relevant categories and tags
- Write engaging excerpts for social sharing
- Use proper markdown formatting
- Include images with alt text when relevant

## Pages

### Static Page Creation
- **Location**: Root directory
- **Naming**: `page-name.markdown` (descriptive, lowercase, hyphens)
- **Layout**: Usually `page` or `default`

### Front Matter for Pages
```yaml
---
layout: page
title: "Page Title"
permalink: /page-url/
description: "Meta description for SEO"
---
```

## Content Guidelines

### Writing Style
- Professional but approachable tone
- Clear, concise language
- Use active voice when possible
- Break up long paragraphs
- Include relevant examples and code snippets

### SEO Considerations
- Include focus keywords naturally
- Use descriptive headings (H2, H3, etc.)
- Write compelling meta descriptions
- Use internal and external links appropriately
- Optimize images with alt text

### Code Examples
- Use syntax highlighting with language specification
- Include comments for complex code
- Provide context and explanation
- Test code examples before publishing

## Image Handling

### Image Storage
- **Location**: `assets/images/` directory
- **Naming**: Descriptive, lowercase, hyphens
- **Formats**: Prefer WebP, fallback to PNG/JPG

### Image Usage
```markdown
![Alt text description]({{ '/assets/images/image-name.webp' | relative_url }})
```

### Optimization
- Compress images for web
- Use appropriate dimensions
- Include descriptive alt text
- Consider mobile responsiveness