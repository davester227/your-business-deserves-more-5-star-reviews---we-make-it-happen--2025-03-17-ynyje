# FiveStars Landing Page Maintenance Guide

This guide will help you maintain and customize the FiveStars landing page. Whether you're new to web development or need a quick reference, follow these instructions to make common updates safely and effectively.

## Table of Contents
- [Updating Text and Styling](#updating-text-and-styling)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains your logo and navigation menu. To update:

1. **Logo Text**: Find this line and change "FiveStars" to your brand name:
```html
<a href="/" class="text-xl font-bold tracking-tight">FiveStars</a>
```

2. **Navigation Menu Items**: Located in the header's `<nav>` section:
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">Benefits</a>
    <a href="#faq" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">FAQ</a>
</div>
```

### Hero Section
The main headline and subheading are in the first `<section>` after `<main>`:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight tracking-tight mb-8">
    Your Business Deserves More 5-Star Reviews — We Make It Happen.
</h1>
<p class="text-xl md:text-2xl text-gray-600 mb-12 leading-relaxed">
    More Reviews. More Customers. We Make It Simple.
</p>
```

#### Understanding Tailwind Classes:
- `text-4xl`: Large text on mobile
- `md:text-5xl`: Larger text on medium screens
- `lg:text-6xl`: Largest text on large screens
- `mb-8`: Margin bottom spacing
- `text-gray-600`: Gray text color

### Features Section
Each feature card follows this structure:
```html
<div class="bg-white p-8 rounded-2xl shadow-sm hover:shadow-md transition-shadow duration-300">
    <div class="w-12 h-12 bg-black rounded-full flex items-center justify-center mb-6">
        <!-- Icon SVG here -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Feature Title</h3>
    <p class="text-gray-600">Feature description text.</p>
</div>
```

To add a new feature card, copy this entire block and paste it within the `grid grid-cols-1 md:grid-cols-3 gap-8` container.

## Managing Links

### External Links
The landing page contains several external links that need updating:

1. **Trial Button Links**: Search for all instances of:
```html
<a href="https://fivestarsmarketing.com"
```
Replace with your actual signup URL.

2. **Email Link**: In the footer, update:
```html
<a href="mailto:join@fivestarsmarketing.com"
```
Replace with your contact email.

### Internal Navigation
Internal links use anchor tags (#) to scroll to sections:

```html
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
```

Ensure these IDs match their corresponding sections:
```html
<section id="features">
<section id="benefits">
<section id="faq">
```

## Adding Privacy and Terms Pages

### Step 1: Create New Pages
Create two new files in your project directory:
- `privacy.html`
- `terms.html`

### Step 2: Update Footer Links
Replace the placeholder links in the footer:

```html
<!-- Before -->
<li><a href="#" class="text-gray-600 hover:text-gray-900">Privacy Policy</a></li>
<li><a href="#" class="text-gray-600 hover:text-gray-900">Terms of Service</a></li>

<!-- After -->
<li><a href="privacy.html" class="text-gray-600 hover:text-gray-900">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-600 hover:text-gray-900">Terms of Service</a></li>
```

### Step 3: Maintain Consistent Styling
When creating privacy.html and terms.html, copy these essential elements from index.html:
- The entire `<head>` section
- Header navigation
- Footer
- All Tailwind CSS classes

## Troubleshooting

### Common Issues and Solutions

1. **Broken Navigation**
   - Verify all section IDs match their corresponding links
   - Check for typos in href attributes
   - Ensure sections have the correct id attribute

2. **Responsive Design Issues**
   - Don't remove `md:` or `lg:` prefixes from Tailwind classes
   - Keep the viewport meta tag in the head section
   - Test on multiple screen sizes using browser dev tools

3. **Styling Problems**
   - Maintain the Tailwind CDN link in the head section
   - Keep the Inter font import for consistent typography
   - Preserve all transition and hover effect classes

### Need Help?
If you encounter issues:
1. Check the browser console for errors (F12)
2. Verify all links are properly formatted
3. Ensure all HTML tags are properly closed
4. Maintain the original class structure when making changes

Remember to test all changes across different devices and browsers before deploying to production.