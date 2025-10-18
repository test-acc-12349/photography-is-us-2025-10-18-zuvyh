# Photography Is Us - Landing Page Maintenance & Customization Guide

Welcome! This comprehensive guide will help you maintain and customize the Photography Is Us landing page. Whether you're updating text, fixing links, or adding new pages, we'll walk you through each step with clear instructions and examples.

---

## Table of Contents

1. [Quick Start Overview](#quick-start-overview)
2. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
3. [Fixing and Managing Links](#fixing-and-managing-links)
4. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
5. [Troubleshooting Guide](#troubleshooting-guide)
6. [Best Practices](#best-practices)

---

## Quick Start Overview

### What You're Working With

This landing page uses:
- **HTML** - The structure and content of the page
- **Tailwind CSS** - A utility-first CSS framework for styling (loaded from a CDN)
- **Font Awesome** - Icon library for visual elements
- **JavaScript** - For interactive features like mobile menu and FAQ toggle

### File Structure You'll Need

```
your-project-folder/
├── index.html (main landing page)
├── privacy.html (privacy policy - you'll create this)
├── terms.html (terms & conditions - you'll create this)
└── images/ (optional: for storing local images)
```

### Before You Start

- Open the HTML file in a text editor (we recommend VS Code, Sublime Text, or Notepad++)
- Keep the file structure organized
- Always make a backup before making major changes
- Test changes in a web browser after each modification

---

## Updating Text and Tailwind CSS Classes

### Understanding the Page Structure

The landing page is divided into these main sections:

```
1. Announcement Bar (top notification)
2. Header (navigation)
3. Hero Section (large background image with main message)
4. Features Section (3 feature cards)
5. Benefits Section (Free Delivery, Fast Shipping, Quality Products)
6. CTA Section (Call-to-action)
7. Testimonials Section (customer reviews)
8. FAQ Section (frequently asked questions)
9. Policies Section (shipping & returns)
10. Newsletter Section (email signup)
11. Footer (links and contact info)
```

---

### 1. Updating the Announcement Bar

**Location:** Lines 74-78 (near the top of the `<body>`)

**Current Code:**
```html
<div class="bg-gray-900 text-white py-3 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto flex items-center justify-center gap-2 text-center">
        <i class="fas fa-truck text-yellow-400"></i>
        <p class="text-sm font-medium">Free worldwide shipping on orders over $100 • Fast 5-day delivery</p>
    </div>
</div>
```

**How to Edit:**

To change the announcement text:

1. Find the line with `<p class="text-sm font-medium">Free worldwide shipping...`
2. Replace the text between `>` and `</p>` with your new message
3. Example: `<p class="text-sm font-medium">🎉 New LED Kits Now Available - 20% Off!</p>`

**Tailwind Classes Explained:**
- `bg-gray-900` = Dark gray background color
- `text-white` = White text color
- `py-3` = Padding (space) on top and bottom (3 units)
- `px-4` = Padding on left and right (4 units)
- `sm:px-6` = On small screens and up, use 6 units of padding
- `text-sm` = Small font size
- `font-medium` = Medium font weight (not bold, not thin)
- `text-yellow-400` = Yellow icon color

**To Change Colors:**

Replace color classes like this:
- `bg-gray-900` → `bg-blue-900` (different background)
- `text-white` → `text-gray-100` (different text color)
- `text-yellow-400` → `text-green-400` (different icon color)

---

### 2. Updating the Header/Navigation

**Location:** Lines 81-154

**Current Code (Logo Section):**
```html
<div class="flex-shrink-0 flex items-center gap-2">
    <i class="fas fa-camera text-gray-900 text-2xl"></i>
    <span class="text-xl font-bold text-gray-900">Photography Is Us</span>
</div>
```

**How to Edit the Logo Text:**

1. Find `<span class="text-xl font-bold text-gray-900">Photography Is Us</span>`
2. Replace `Photography Is Us` with your company name
3. Example: `<span class="text-xl font-bold text-gray-900">Pro Photo Gear</span>`

**How to Change the Logo Icon:**

Font Awesome icons are referenced like `<i class="fas fa-camera"></i>`

1. Visit [fontawesome.com/icons](https://fontawesome.com/icons)
2. Search for an icon you like
3. Copy the icon name (e.g., "fa-image", "fa-photo-film")
4. Replace `fa-camera` in the code
5. Example: `<i class="fas fa-photo-film text-gray-900 text-2xl"></i>`

**Updating Navigation Links:**

**Current Navigation Links (Lines 92-97):**
```html
<nav class="hidden md:flex items-center gap-8">
    <a href="#features" class="text-gray-700 hover:text-gray-900 text-sm font-medium smooth-transition">Features</a>
    <a href="#benefits" class="text-gray-700 hover:text-gray-900 text-sm font-medium smooth-transition">Benefits</a>
    <a href="#faq" class="text-gray-700 hover:text-gray-900 text-sm font-medium smooth-transition">FAQ</a>
    <a href="#testimonials" class="text-gray-700 hover:text-gray-900 text-sm font-medium smooth-transition">Reviews</a>
</nav>
```

These links use `#` (anchor links) to jump to sections on the same page. They're already set up correctly.

**To Add a New Navigation Link:**

1. Add a new line before `</nav>`:
   ```html
   <a href="#blog" class="text-gray-700 hover:text-gray-900 text-sm font-medium smooth-transition">Blog</a>
   ```

2. Make sure a section with `id="blog"` exists elsewhere on the page

**Updating the "Buy Now" Button:**

**Current Code (Lines 99-102):**
```html
<a href="https://led.com" class="btn-primary text-white px-6 py-2 rounded-lg text-sm font-semibold">Buy Now</a>
```

To change where the button links:
1. Replace `https://led.com` with your actual shop URL
2. Example: `https://www.shopify.com/your-store`

**Tailwind Classes for the Button:**
- `btn-primary` = Custom button style (defined in `<style>` section)
- `text-white` = White text
- `px-6` = Horizontal padding
- `py-2` = Vertical padding
- `rounded-lg` = Rounded corners
- `text-sm` = Small font
- `font-semibold` = Bold text

---

### 3. Updating the Hero Section

**Location:** Lines 157-195

**Current Code:**
```html
<section class="relative w-full h-screen min-h-96 flex items-center justify-center overflow-hidden">
    <div class="absolute inset-0 z-0">
        <img src="https://images.unsplash.com/photo-1504093376055-b3094b674dcb?w=1600&h=900&fit=crop&q=80" alt="Professional photography equipment" class="w-full h-full object-cover">
        <div class="hero-overlay absolute inset-0"></div>
    </div>

    <div class="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center fade-in">
        <h1 class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-bold text-white mb-6 leading-tight tracking-tight">
            Photography Is Us
        </h1>
        <p class="text-xl sm:text-2xl md:text-3xl text-gray-100 mb-8 font-light">
            Best Photography Kit
        </p>
        <p class="text-base sm:text-lg text-gray-200 mb-12 max-w-2xl mx-auto">
            Professional-grade equipment designed for photographers who demand excellence
        </p>
```

**How to Update Hero Text:**

1. **Main Heading (h1):** Find and replace `Photography Is Us`
   ```html
   <h1 class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-bold text-white mb-6 leading-tight tracking-tight">
       Your New Heading Here
   </h1>
   ```

2. **Subheading (first p):** Find and replace `Best Photography Kit`
   ```html
   <p class="text-xl sm:text-2xl md:text-3xl text-gray-100 mb-8 font-light">
       Your Subheading Here
   </p>
   ```

3. **Description (second p):** Find and replace the longer description
   ```html
   <p class="text-base sm:text-lg text-gray-200 mb-12 max-w-2xl mx-auto">
       Your description text here
   </p>
   ```

**Understanding Responsive Text Sizes:**

The hero uses responsive sizing that changes based on screen size:
- `text-4xl` = Extra large on mobile
- `sm:text-5xl` = Larger on small screens (640px+)
- `md:text-6xl` = Even larger on medium screens (768px+)
- `lg:text-7xl` = Largest on large screens (1024px+)

**Changing the Hero Background Image:**

1. Find the `<img src="https://images.unsplash.com/photo-1504093376055-b3094b674dcb?w=1600&h=900&fit=crop&q=80"`
2. Replace the URL with your own image URL
3. Keep the dimensions: `w=1600&h=900` for best results
4. Example: `<img src="https://your-domain.com/images/hero.jpg"`

**To Use a Local Image Instead:**

1. Save your image in a folder (e.g., `images/hero.jpg`)
2. Replace the full URL with the relative path:
   ```html
   <img src="images/hero.jpg" alt="Professional photography equipment"
   ```

**Updating Hero Buttons:**

**Current Code (Lines 185-193):**
```html
<a href="https://led.com" class="btn-primary text-white px-8 py-4 rounded-lg text-lg font-semibold inline-flex items-center justify-center gap-2 hover:shadow-2xl">
    <span>Explore Our Collection</span>
    <i class="fas fa-arrow-right"></i>
</a>
<button class="bg-white text-gray-900 px-8 py-4 rounded-lg text-lg font-semibold smooth-transition hover:bg-gray-100 inline-flex items-center justify-center gap-2">
    <i class="fas fa-play-circle"></i>
    <span>Watch Demo</span>
</button>
```

To change button text:
- First button: Replace `Explore Our Collection` with your text
- Second button: Replace `Watch Demo` with your text

To change button links:
- First button: Change `href="https://led.com"` to your URL
- Second button: Add `onclick="location.href='your-url'"` to make it a link

---

### 4. Updating the Features Section

**Location:** Lines 198-290

**Current Code Structure:**
```html
<section id="features" class="py-16 md:py-24 px-4 sm:px-6 lg:px-8 bg-white">
    <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-gray-900 mb-4">
                Premium Photography Essentials
            </h2>
            <p class="text-lg text-gray-600 max-w-2xl mx-auto">
                Everything you need to capture stunning moments with professional-quality results
            </p>
        </div>
```

**How to Update Section Title:**

1. Find `<h2>Premium Photography Essentials</h2>`
2. Replace with your title
3. Example: `<h2>Our Essential Gear</h2>`

**How to Update Section Description:**

1. Find the paragraph below the heading
2. Replace the text between `>` and `</p>`

**Updating Individual Feature Cards:**

There are 3 feature cards (LED Lighting, Tripods, Pro Equipment). Here's how to edit one:

**Current LED Lighting Card (Lines 243-263):**
```html
<div class="feature-card bg-white border border-gray-200 rounded-2xl p-8 smooth-transition">
    <div class="bg-gradient-to-br from-yellow-100 to-yellow-50 w-16 h-16 rounded-xl flex items-center justify-center mb-6">
        <i class="fas fa-lightbulb text-yellow-600 text-2xl"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-3">LED Lighting</h3>
    <p class="text-gray-600 mb-4">
        Professional-grade LED lighting systems that provide consistent, flicker-free illumination for perfect shots in any condition.
    </p>
    <ul class="space-y-2 text-sm text-gray-600">
        <li class="flex items-center gap-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Adjustable color temperature</span>
        </li>
        <li class="flex items-center gap-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Dimming capabilities</span>
        </li>
        <li class="flex items-center gap-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Energy efficient</span>
        </li>
    </ul>
</div>
```

**To Edit This Card:**

1. **Change the Icon:**
   - Find `<i class="fas fa-lightbulb text-yellow-600 text-2xl"></i>`
   - Replace `fa-lightbulb` with a new icon (search [fontawesome.com](https://fontawesome.com/icons))
   - Example: `<i class="fas fa-sun text-yellow-600 text-2xl"></i>`

2. **Change Icon Background Color:**
   - Find `from-yellow-100 to-yellow-50`
   - Replace with new colors: `from-blue-100 to-blue-50`
   - Find `text-yellow-600`
   - Replace with: `text-blue-600`

3. **Change Card Title:**
   - Find `<h3 class="text-2xl font-bold text-gray-900 mb-3">LED Lighting</h3>`
   - Replace `LED Lighting` with your title

4. **Change Card Description:**
   - Find the paragraph starting with "Professional-grade LED..."
   - Replace with your description

5. **Update Feature List:**
   - Each `<li>` contains a feature
   - Replace "Adjustable color temperature", "Dimming capabilities", "Energy efficient" with your features
   - Keep the `<i class="fas fa-check text-green-500"></i>` for the checkmark

**Complete Example - Changing the LED Lighting Card to a "Cameras" Card:**

```html
<div class="feature-card bg-white border border-gray-200 rounded-2xl p-8 smooth-transition">
    <div class="bg-gradient-to-br from-red-100 to-red-50 w-16 h-16 rounded-xl flex items-center justify-center mb-6">
        <i class="fas fa-camera text-red-600 text-2xl"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-3">Professional Cameras</h3>
    <p class="text-gray-600 mb-4">
        High-end DSLR and mirrorless cameras with cutting-edge sensors and autofocus systems.
    </p>
    <ul class="space-y-2 text-sm text-gray-600">
        <li class="flex items-center gap-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Full-frame sensors</span>
        </li>
        <li class="flex items-center gap-2">
            <i class="fas fa-check text-green-500"></i>
            <span>4K video capability</span>
        </li>
        <li class="flex items-center gap-2">
            <i class="fas fa-check text-green-500"></i>
            <span>Advanced autofocus</span>
        </li>
    </ul>
</div>
```

---

### 5. Updating the Benefits Section

**Location:** Lines 293-430

This section has 3 benefit blocks with alternating text/image layouts.

**Current Structure (Free Delivery Block):**
```html
<div class="py-12 md:py-20 px-4 sm:px-6 lg:px-8 bg-white">
    <div class="max-w-7xl mx-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 md:gap-12 items-center">
            <div class="order-2 md:order-1">
                <img src="https://images.unsplash.com/photo-1556740714-a8395b3bf30f?w=800&h=600&fit=crop&q=80" alt="Free delivery service" class="w-full h-auto rounded-2xl shadow-lg object-cover">
            </div>
            <div class="order-1 md:order-2">
                <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-gray-900 mb-6 leading-tight">
                    Free Delivery
                </h2>
```

**How to Update Benefit Title:**

1. Find the `<h2>` tag in the benefit block
2. Replace the text
3. Example: `<h2>Free Worldwide Shipping</h2>`

**How to Update Benefit Description:**

1. Find the first `<p>` after the title
2. Replace the text between `>` and `</p>`

**How to Update Benefit List Items:**

**Current List (Lines 327-352):**
```html
<ul class="space-y-4 mb-8">
    <li class="flex items-start gap-4">
        <div class="bg-green-100 rounded-full p-3 flex-shrink-0 mt-1">
            <i class="fas fa-check text-green-600"></i>
        </div>
        <div>
            <p class="font-semibold text-gray-900">Worldwide Coverage</p>
            <p class="text-gray-600 text-sm">Delivery to over 150 countries</p>
        </div>
    </li>
```

For each list item:
- Change `Worldwide Coverage` to your benefit title
- Change `Delivery to over 150 countries` to your benefit description

**How to Change Benefit Images:**

1. Find `<img src="https://images.unsplash.com/photo-1556740714-a8395b3bf30f?w=800&h=600&fit=crop&q=80"`
2. Replace with your image URL
3. Update the `alt` text to describe your image

**Changing Colors for Different Benefit Blocks:**

The second benefit (Fast Shipping) uses blue:
- `bg-green-100` → `bg-blue-100`
- `text-green-600` → `text-blue-600`

The third benefit (Quality Products) uses purple:
- `bg-green-100` → `bg-purple-100`
- `text-green-600` → `text-purple-600`

**How to Change Benefit Icons:**

1. Find `<i class="fas fa-check text-green-600"></i>`
2. Replace `fa-check` with your icon
3. Examples: `fa-truck`, `fa-rocket`, `fa-award`, `fa-shield-alt`

---

### 6. Updating the CTA Section

**Location:** Lines 433-461

**Current Code:**
```html
<h2 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-white mb-6 leading-tight">
    Ready to Elevate Your Photography?
</h2>
<p class="text-lg md:text-xl text-gray-100 mb-8 max-w-2xl mx-auto">
    Join thousands of professional photographers who trust us for their equipment needs. Start your journey with the best photography kit available.
</p>
```

**How to Update:**

1. Replace the heading with your CTA message
2. Replace the paragraph with your CTA description
3. Update button text and links (same as hero section)

**Changing the Background Image:**

1. Find `<img src="https://images.unsplash.com/photo-1516035069371-29a08e8c1e4d?w=1600&h=600&fit=crop&q=80"`
2. Replace with your image URL

---

### 7. Updating Testimonials Section

**Location:** Lines 464-534

**Current Structure:**
```html
<section id="testimonials" class="py-16 md:py-24 px-4 sm:px-6 lg:px-8 bg-gray-50">
    <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-gray-900 mb-4">
                Loved by Photographers
            </h2>
```

**How to Update Section Title:**

1. Find and replace `Loved by Photographers`

**How to Update Individual Testimonials:**

**Current Testimonial Card (Lines 500-517):**
```html
<div class="testimonial-card">
    <div class="flex items-center gap-1 mb-4">
        <i class="fas fa-star star-rating"></i>
        <i class="fas fa-star star-rating"></i>
        <i class="fas fa-star star-rating"></i>
        <i class="fas fa-star star-rating"></i>
        <i class="fas fa-star star-rating"></i>
    </div>
    <p class="text-gray-700 mb-6 leading-relaxed">
        "Photography Is Us has completely transformed my business. The quality of their equipment is unmatched, and the customer service is exceptional. Highly recommended!"
    </p>
    <div class="flex items-center gap-4">
        <div class="w-12 h-12 bg-gradient-to-br from-blue-400 to-blue-600 rounded-full flex items-center justify-center text-white font-bold">
            JM
        </div>
        <div>
            <p class="font-semibold text-gray-900">James Mitchell</p>
            <p class="text-sm text-gray-600">Professional Photographer</p>
        </div>
    </div>
</div>
```

**To Edit a Testimonial:**

1. **Change the Quote:**
   - Find the text in quotes
   - Replace with your testimonial

2. **Change the Initials:**
   - Find `JM` (or whatever initials are there)
   - Replace with customer initials

3. **Change Avatar Color:**
   - Find `from-blue-400 to-blue-600`
   - Replace with other colors: `from-pink-400 to-pink-600`, `from-green-400 to-green-600`

4. **Change Customer Name:**
   - Find `James Mitchell`
   - Replace with actual name

5. **Change Customer Title:**
   - Find `Professional Photographer`
   - Replace with customer's profession

**To Change Star Rating:**

If a testimonial deserves fewer stars, remove star icons:
```html
<!-- 4 stars instead of 5 -->
<i class="fas fa-star star-rating"></i>
<i class="fas fa-star star-rating"></i>
<i class="fas fa-star star-rating"></i>
<i class="fas fa-star star-rating"></i>
```

---

### 8. Updating FAQ Section

**Location:** Lines 537-635

**Current Structure:**
```html
<section id="faq" class="py-16 md:py-24 px-4 sm:px-6 lg:px-8 bg-white">
    <div class="max-w-4xl mx-auto">
        <div class="text-center mb-16">
            <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-gray-900 mb-4">
                Frequently Asked Questions
            </h2>
```

**How to Update FAQ Title:**

1. Find and replace `Frequently Asked Questions`

**How to Update Individual FAQ Items:**

**Current FAQ Item (Lines 556-567):**
```html
<div class="faq-item">
    <button class="w-full py-6 px-6 flex items-center justify-between hover:bg-gray-50 smooth-transition" onclick="toggleFAQ(this)">
        <h3 class="text-lg font-semibold text-gray-900 text-left">
            What warranty do your products come with?
        </h3>
        <i class="fas fa-chevron-down faq-icon text-gray-600"></i>
    </button>
    <div class="faq-content px-6 pb-6">
        <p class="text-gray-600 leading-relaxed">
            All our products come with a comprehensive manufacturer's warranty ranging from 1 to 3 years depending on the item. We also offer extended warranty options for additional peace of mind. Our team is always ready to help with any warranty claims.
        </p>
    </div>
</div>
```

**To Edit an FAQ Item:**

1. **Change the Question:**
   - Find the text in `<h3>`
   - Replace with your question

2. **Change the Answer:**
   - Find the text in the `<p>` inside `faq-content`
   - Replace with your answer

**To Add a New FAQ Item:**

1. Copy the entire `<div class="faq-item">` block
2. Paste it before `</div>` (before the closing of the section)
3. Update the question and answer text
4. Example:

```html
<div class="faq-item">
    <button class="w-full py-6 px-6 flex items-center justify-between hover:bg-gray-50 smooth-transition" onclick="toggleFAQ(this)">
        <h3 class="text-lg font-semibold text-gray-900 text-left">
            Do you offer payment plans?
        </h3>
        <i class="fas fa-chevron-down faq-icon text-gray-600"></i>
    </button>
    <div class="faq-content px-6 pb-6">
        <p class="text-gray-600 leading-relaxed">
            Yes, we offer flexible payment plans for purchases over $500. Contact our sales team for details.
        </p>
    </div>
</div>
```

---

### 9. Updating Policies Section

**Location:** Lines 638-693

**Current Structure:**
```html
<div class="bg-white rounded-2xl p-8 border border-gray-200">
    <div class="flex items-center gap-4 mb-6">
        <div class="bg-blue-100 w-16 h-16 rounded-xl flex items-center justify-center">
            <i class="fas fa-shipping-fast text-blue-600 text-2xl"></i>
        </div>
        <h3 class="text-2xl font-bold text-gray-900">Shipping Policy</h3>
    </div>
```

**How to Update Policy Title:**

1. Find the `<h3>` tag
2. Replace `Shipping Policy` with your title

**How to Update Policy Content:**

1. Find the `<p>` tag with the policy description
2. Replace the text

**How to Update Policy List Items:**

Find the `<ul>` section and update each `<li>`:
```html
<li class="flex items-start gap-3">
    <i class="fas fa-check-circle text-green-500 mt-0.5 flex-shrink-0"></i>
    <span>Free shipping on all orders worldwide</span>
</li>
```

Replace the text in `<span>` with your policy points.

---

### 10. Updating Newsletter Section

**Location:** Lines 696-710

**Current Code:**
```html
<h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-white mb-4">
    Stay Updated
</h2>
<p class="text-lg text-gray-300 mb-8">
    Subscribe to our newsletter for exclusive deals, photography tips, and new product announcements
</p>
```

**How to Update:**

1. Replace `Stay Updated` with your heading
2. Replace the paragraph text with your description

**Updating Form Placeholder:**

```html
<input type="email" placeholder="Enter your email" required class="flex-1 px-6 py-4 rounded-lg focus:outline-none focus:ring-2 focus:ring-gray-400 text-gray-900" aria-label="Email address">
```

Replace `Enter your email` with your placeholder text.

---

### 11. Updating Footer

**Location:** Lines 713-805

**Updating Company Info:**

```html
<div class="flex items-center gap-2 mb-4">
    <i class="fas fa-camera text-yellow-400 text-2xl"></i>
    <span class="text-xl font-bold text-white">Photography Is Us</span>
</div>
<p class="text-sm text-gray-400 mb-6">
    Premium photography equipment for professionals and enthusiasts worldwide.
</p>
```

1. Replace `Photography Is Us` with your company name
2. Replace the description text

**Updating Footer Links:**

**Current Quick Links Section (Lines 738-755):**
```html
<div>
    <h4 class="text-white font-semibold mb-6">Quick Links</h4>
    <ul class="space-y-3">
        <li>
            <a href="#features" class="text-gray-400 hover:text-white smooth-transition text-sm">
                Features
            </a>
        </li>
```

To add or change a footer link:
1. Find the section
2. Update the `href` attribute
3. Update the link text

**Updating Contact Information:**

**Current Contact Section (Lines 771-790):**
```html
<li class="flex items-start gap-3">
    <i class="fas fa-envelope text-yellow-400 mt-1 flex-shrink-0"></i>
    <div>
        <p class="text-sm text-gray-400">Email</p>
        <a href="mailto:admin@led.com" class="text-white hover:text-yellow-400 smooth-transition font-medium">
            admin@led.com
        </a>
    </div>
</li>
```

1. Replace `admin@led.com` with your email
2. Replace phone number and address with your information

**Updating Copyright Year:**

**Current Code (Line 802):**
```html
<p class="text-sm text-gray-400">
    &copy; 2024 Photography Is Us. All rights reserved.
</p>
```

Replace `2024` with the current year and `Photography Is Us` with your company name.

---

## Fixing and Managing Links

### Understanding Link Types in This Page

There are three types of links in this landing page:

1. **Anchor Links** (jump to sections on same page)
   - Format: `href="#section-id"`
   - Example: `href="#features"` jumps to the Features section

2. **External Links** (go to other websites)
   - Format: `href="https://website.com"`
   - Example: `href="https://led.com"` goes to external shop

3. **Email Links** (open email client)
   - Format: `href="mailto:email@example.com"`
   - Example: `href="mailto:admin@led.com"`

---

### Identifying All Current Links

Here's a complete list of all links in the page and where they are:

**Navigation Links (Header):**
```
Line 92: href="#features" → Features section
Line 93: href="#benefits" → Benefits section  
Line 94: href="#faq" → FAQ section
Line 95: href="#testimonials" → Testimonials section
```

**Button Links:**
```
Line 102: href="https://led.com" → External shop (NEEDS UPDATE)
Line 103: Search input - no link
Line 125: href="https://led.com" → External shop (NEEDS UPDATE)
Line 171: href="https://led.com" → External shop (NEEDS UPDATE)
Line 177: onclick="Watch Demo" → JavaScript function
```

**CTA Section Links:**
```
Line 447: href="https://led.com" → External shop (NEEDS UPDATE)
Line 451: onclick="Contact Us" → JavaScript function
```

**Policy Section Links:**
```
Line 357: href="https://led.com" → External shop (NEEDS UPDATE)
Line 397: href="https://led.com" → External shop (NEEDS UPDATE)
Line 427: href="https://led.com" → External shop (NEEDS UPDATE)
```

**Footer Links:**
```
Line 748: href="#features" → Features section
Line 749: href="#benefits" → Benefits section
Line 750: href="#testimonials" → Testimonials section
Line 751: href="#faq" → FAQ section
Line 752: href="https://led.com" → External shop (NEEDS UPDATE)
Line 759: href="#" → Placeholder (NEEDS UPDATE)
Line 761: href="#" → Placeholder (NEEDS UPDATE)
Line 763: href="#" → Placeholder (NEEDS UPDATE)
Line 765: href="#" → Placeholder (NEEDS UPDATE)
Line 767: href="#" → Placeholder (NEEDS UPDATE)
Line 774: href="mailto:admin@led.com" → Email (UPDATE WITH YOUR EMAIL)
Line 778: href="tel:+1234567890" → Phone (UPDATE WITH YOUR PHONE)
Line 800: href="#" → Placeholder (NEEDS UPDATE)
Line 804: href="#" → Placeholder (NEEDS UPDATE)
Line 806: href="#" → Placeholder (NEEDS UPDATE)
```

---

### Step-by-Step: Updating the Shop Link

**What to Change:** All `https://led.com` links should point to your actual shop

**Current Code Example (Line 102):**
```html
<a href="https://led.com" class="btn-primary text-white px-6 py-2 rounded-lg text-sm font-semibold">Buy Now</a>
```

**Step 1: Identify Your Shop URL**

Determine where your shop is:
- Your own website: `https://www.yourshop.com`
- Shopify store: `https://yourstore.myshopify.com`
- Amazon: `https://www.amazon.com/your-storefront`
- Etsy: `https://www.etsy.com/shop/yourshop`

**Step 2: Find and Replace**

Use your text editor's Find & Replace feature:

1. **In VS Code:**
   - Press `Ctrl+H` (Windows) or `Cmd+H` (Mac)
   - Find: `https://led.com`
   - Replace with: `https://www.yourshop.com`
   - Click "Replace All"

2. **In Notepad++:**
   - Press `Ctrl+H`
   - Find: `https://led.com`
   - Replace with: `https://www.yourshop.com`
   - Click "Replace All"

3. **Manual Method:**
   - Use `Ctrl+F` to find each instance
   - Replace one by one

**Step 3: Verify**

After replacing, check a few links:
- Line 102: Should now show your URL
- Line 125: Should now show your URL
- Line 171: Should now show your URL

**Example of Updated Code:**
```html
<a href="https://www.photoshop.com" class="btn-primary text-white px-6 py-2 rounded-lg text-sm font-semibold">Buy Now</a>
```

---

### Step-by-Step: Updating Email Links

**Current Code (Line 774):**
```html
<a href="mailto:admin@led.com" class="text-white hover:text-yellow-400 smooth-transition font-medium">
    admin@led.com
</a>
```

**To Update:**

1. Replace `admin@led.com` in the `href` with your email:
   ```html
   <a href="mailto:your-email@yourcompany.com" class="text-white hover:text-yellow-400 smooth-transition font-medium">
       your-email@yourcompany.com
   </a>
   ```

2. Also update the email text displayed (after the `>`)

**Important:** Make sure both the `href` and the displayed text match your email.

**Using Find & Replace for Email:**

1. Open Find & Replace
2. Find: `admin@led.com`
3. Replace with: `your-email@yourcompany.com`
4. Replace All

---

### Step-by-Step: Updating Phone Links

**Current Code (Line 778):**
```html
<a href="tel:+1234567890" class="text-white hover:text-yellow-400 smooth-transition font-medium">
    +1 (234) 567-890
</a>
```

**To Update:**

1. Replace the phone number in `href`:
   ```html
   <a href="tel:+1-555-123-4567" class="text-white hover:text-yellow-400 smooth-transition font-medium">
       +1 (555) 123-4567
   </a>
   ```

2. Update the displayed phone number to match

**Important:** 
- `href` format: `tel:+1-555-123-4567` (use dashes, start with +1 for US)
- Display format: `+1 (555) 123-4567` (can use any format for readability)

**International Phone Numbers:**

For international numbers:
- UK: `href="tel:+44-20-7946-0958"` 
- Germany: `href="tel:+49-30-123456"`
- Australia: `href="tel:+61-2-1234-5678"`

---

### Step-by-Step: Updating Placeholder Links

**What are Placeholder Links?**

These are links with `href="#"` that don't go anywhere:

```html
<a href="#" class="text-gray-400 hover:text-white smooth-transition text-sm">
    Contact Us
</a>
```

**To Fix Them:**

**Option 1: Link to a Real Page**

If you have a Contact page:
```html
<a href="contact.html" class="text-gray-400 hover:text-white smooth-transition text-sm">
    Contact Us
</a>
```

**Option 2: Link to External Site**

```html
<a href="https://www.yourcompany.com/blog" class="text-gray-400 hover:text-white smooth-transition text-sm">
    Blog
</a>
```

**Option 3: Make it a Button with JavaScript**

```html
<button onclick="location.href='https://www.yourcompany.com'" class="text-gray-400 hover:text-white smooth-transition text-sm">
    Contact Us
</button>
```

**Complete List of Placeholder Links to Fix:**

| Line | Current Text | What to Do |
|------|-------------|-----------|
| 759 | Contact Us | Link to contact.html or external contact page |
| 761 | Blog | Link to blog.html or external blog |
| 763 | Privacy Policy | Link to privacy.html (see next section) |
| 765 | Terms & Conditions | Link to terms.html (see next section) |
| 767 | Shipping Info | Link to shipping.html or external page |
| 800 | Privacy Policy | Link to privacy.html |
| 804 | Terms of Service | Link to terms.html |
| 806 | Cookie Settings | Link to cookie settings page |

---

### Example: Fixing Multiple Links at Once

**Scenario:** You need to update:
1. Shop link from `https://led.com` to `https://myshop.com`
2. Email from `admin@led.com` to `hello@myshop.com`
3. Contact page from `#` to `contact.html`

**Using Find & Replace (3 times):**

1. **First replacement:**
   - Find: `https://led.com`
   - Replace: `https://myshop.com`
   - Replace All

2. **Second replacement:**
   - Find: `admin@led.com`
   - Replace: `hello@myshop.com`
   - Replace All

3. **Third replacement:**
   - Find: `<a href="#" class="text-gray-400 hover:text-white smooth-transition text-sm">Contact Us</a>`
   - Replace: `<a href="contact.html" class="text-gray-400 hover:text-white smooth-transition text-sm">Contact Us</a>`
   - Replace All

---

## Linking Privacy and Terms Pages

### Understanding What You Need

You need to create two new HTML files:
1. `privacy.html` - Privacy Policy page
2. `terms.html` - Terms & Conditions page

Then link them from the main `index.html` file.

---

### Step 1: Create the Privacy Policy Page

**Create a new file called `privacy.html`:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Photography Is Us - Privacy Policy">
    <title>Privacy Policy - Photography Is Us</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Sora:wght@400;500;600;700&display=swap');
        * {
            font-family: 'Sora', sans-serif;
        }
    </style>
</head>
<body class="bg-white text-gray-900">
    <!-- Header (same as index.html) -->
    <header class="sticky top-0 z-30 bg-white border-b border-gray-100 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex-shrink-0 flex items-center gap-2">
                    <i class="fas fa-camera text-gray-900 text-2xl"></i>
                    <span class="text-xl font-bold text-gray-900">Photography Is Us</span>
                </div>
                <nav class="hidden md:flex items-center gap-8">
                    <a href="index.html" class="text-gray-700 hover:text-gray-900 text-sm font-medium">Home</a>
                </nav>
                <a href="index.html" class="text-gray-700 hover:text-gray-900 text-sm font-medium md:hidden">Back</a>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <section class="py-16 md:py-24 px-4 sm:px-6 lg:px-8 bg-white">
        <div class="max-w-4xl mx-auto">
            <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Privacy Policy</h1>
            
            <div class="prose prose-lg max-w-none text-gray-600 space-y-6">
                <p>
                    <strong>Last Updated:</strong> January 2024
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">1. Introduction</h2>
                <p>
                    Photography Is Us ("we," "us," "our," or "Company") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and otherwise handle your personal information when you visit our website, use our services, or make purchases from us.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">2. Information We Collect</h2>
                <p>We may collect information about you in various ways, including:</p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Information you provide directly (name, email, address, phone number)</li>
                    <li>Payment information (credit card details, billing address)</li>
                    <li>Information automatically collected (IP address, browser type, pages visited)</li>
                    <li>Information from cookies and similar tracking technologies</li>
                </ul>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">3. How We Use Your Information</h2>
                <p>We use the information we collect for purposes including:</p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Processing and fulfilling your orders</li>
                    <li>Sending you promotional emails and newsletters</li>
                    <li>Improving our website and services</li>
                    <li>Preventing fraud and enhancing security</li>
                    <li>Complying with legal obligations</li>
                </ul>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">4. Sharing Your Information</h2>
                <p>
                    We do not sell your personal information. We may share your information with:
                </p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Service providers who assist us in operating our website and conducting our business</li>
                    <li>Law enforcement when required by law</li>
                    <li>Business partners with your consent</li>
                </ul>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">5. Data Security</h2>
                <p>
                    We implement appropriate technical and organizational measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction. However, no method of transmission over the internet is 100% secure.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">6. Your Rights</h2>
                <p>Depending on your location, you may have the right to:</p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Access your personal information</li>
                    <li>Correct inaccurate data</li>
                    <li>Request deletion of your data</li>
                    <li>Opt-out of marketing communications</li>
                    <li>Data portability</li>
                </ul>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">7. Cookies</h2>
                <p>
                    We use cookies to enhance your experience on our website. You can control cookie settings through your browser preferences. Disabling cookies may affect website functionality.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">8. Third-Party Links</h2>
                <p>
                    Our website may contain links to third-party websites. We are not responsible for their privacy practices. We encourage you to review their privacy policies.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">9. Children's Privacy</h2>
                <p>
                    Our website is not intended for children under 13 years of age. We do not knowingly collect personal information from children under 13.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">10. Changes to This Policy</h2>
                <p>
                    We may update this Privacy Policy from time to time. We will notify you of any changes by posting the new policy on this page with an updated "Last Updated" date.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">11. Contact Us</h2>
                <p>
                    If you have questions about this Privacy Policy or our privacy practices, please contact us at:
                </p>
                <p>
                    <strong>Photography Is Us</strong><br>
                    Email: <a href="mailto:admin@led.com" class="text-blue-600 hover:underline">admin@led.com</a><br>
                    Phone: <a href="tel:+1234567890" class="text-blue-600 hover:underline">+1 (234) 567-890</a><br>
                    Address: 123 Photography Lane, Creative City, CC 12345
                </p>
            </div>
        </div>
    </section>

    <!-- Footer (same as index.html) -->
    <footer class="bg-gray-900 text-gray-300 py-16 px-4 sm:px-6 lg:px-8">
        <div class="max-w-7xl mx-auto">
            <div class="text-center">
                <p class="text-sm text-gray-400">
                    &copy; 2024 Photography Is Us. All rights reserved.
                </p>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

### Step 2: Create the Terms & Conditions Page

**Create a new file called `terms.html`:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Photography Is Us - Terms & Conditions">
    <title>Terms & Conditions - Photography Is Us</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Sora:wght@400;500;600;700&display=swap');
        * {
            font-family: 'Sora', sans-serif;
        }
    </style>
</head>
<body class="bg-white text-gray-900">
    <!-- Header (same as index.html) -->
    <header class="sticky top-0 z-30 bg-white border-b border-gray-100 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex-shrink-0 flex items-center gap-2">
                    <i class="fas fa-camera text-gray-900 text-2xl"></i>
                    <span class="text-xl font-bold text-gray-900">Photography Is Us</span>
                </div>
                <nav class="hidden md:flex items-center gap-8">
                    <a href="index.html" class="text-gray-700 hover:text-gray-900 text-sm font-medium">Home</a>
                </nav>
                <a href="index.html" class="text-gray-700 hover:text-gray-900 text-sm font-medium md:hidden">Back</a>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <section class="py-16 md:py-24 px-4 sm:px-6 lg:px-8 bg-white">
        <div class="max-w-4xl mx-auto">
            <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Terms & Conditions</h1>
            
            <div class="prose prose-lg max-w-none text-gray-600 space-y-6">
                <p>
                    <strong>Last Updated:</strong> January 2024
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">1. Agreement to Terms</h2>
                <p>
                    By accessing and using this website and purchasing products from Photography Is Us, you agree to be bound by these Terms & Conditions. If you do not agree to any part of these terms, you may not use our website or purchase from us.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">2. Use License</h2>
                <p>
                    Permission is granted to temporarily download one copy of the materials (information or software) on Photography Is Us's website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                </p>
                <ul class="list-disc list-inside space-y-2 ml-4">
                    <li>Modify or copy the materials</li>
                    <li>Use the materials for any commercial purpose or for any public display</li>
                    <li>Attempt to decompile or reverse engineer any software contained on the website</li>
                    <li>Remove any copyright or other proprietary notations from the materials</li>
                    <li>Transfer the materials to another person or "mirror" the materials on any other server</li>
                </ul>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">3. Product Information</h2>
                <p>
                    We strive to provide accurate product descriptions and pricing. However, we do not warrant that product descriptions, pricing, or other content is accurate, complete, reliable, current, or error-free. If a product offered by Photography Is Us is not as described, your sole remedy is to return it in unused condition.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">4. Pricing and Availability</h2>
                <p>
                    All prices are subject to change without notice. We reserve the right to limit quantities and to discontinue any product. Products are subject to availability, and we reserve the right to discontinue any product at any time.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">5. Order Acceptance</h2>
                <p>
                    We reserve the right to refuse any order. We reserve the right to discontinue any product at any time. We reserve the right to limit the order quantity of any product. We reserve the right to revise our prices at any time without notice.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">6. Return and Refund Policy</h2>
                <p>
                    We offer a 30-day return window from the date of purchase. Products must be in their original, unused condition with all original packaging and documentation. Refunds will be processed within 5-7 business days of receiving the returned item.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">7. Shipping Policy</h2>
                <p>
                    We offer free shipping on all orders worldwide. Standard delivery takes 5 business days. Express shipping options are available at checkout. We are not responsible for delays caused by customs or local postal services.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">8. Warranty Disclaimer</h2>
                <p>
                    The materials on Photography Is Us's website are provided on an 'as is' basis. Photography Is Us makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">9. Limitations of Liability</h2>
                <p>
                    In no event shall Photography Is Us or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on Photography Is Us's website.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">10. Accuracy of Materials</h2>
                <p>
                    The materials appearing on Photography Is Us's website could include technical, typographical, or photographic errors. Photography Is Us does not warrant that any of the materials on its website are accurate, complete, or current. Photography Is Us may make changes to the materials contained on its website at any time without notice.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">11. Links</h2>
                <p>
                    Photography Is Us has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by Photography Is Us of the site. Use of any such linked website is at the user's own risk.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">12. Modifications</h2>
                <p>
                    Photography Is Us may revise these terms and conditions for its website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms and conditions.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">13. Governing Law</h2>
                <p>
                    These terms and conditions are governed by and construed in accordance with the laws of the jurisdiction in which Photography Is Us operates, and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                </p>

                <h2 class="text-2xl font-bold text-gray-900 mt-8">14. Contact Us</h2>
                <p>
                    If you have any questions about these Terms & Conditions, please contact us at:
                </p>
                <p>
                    <strong>Photography Is Us</strong><br>
                    Email: <a href="mailto:admin@led.com" class="text-blue-600 hover:underline">admin@led.com</a><br>
                    Phone: <a href="tel:+1234567890" class="text-blue-600 hover:underline">+1 (234) 567-890</a><br>
                    Address: 123 Photography Lane, Creative City, CC 12345
                </p>
            </div>
        </div>
    </section>

    <!-- Footer (same as index.html) -->
    <footer class="bg-gray-900 text-gray-300 py-16 px-4 sm:px-6 lg:px-8">
        <div class="max-w-7xl mx-auto">
            <div class="text-center">
                <p class="text-sm text-gray-400">
                    &copy; 2024 Photography Is Us. All rights reserved.
                </p>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

### Step 3: Update Links in index.html

Now you need to update the links in `index.html` to point to these new pages.

**Find and Update Footer Privacy Policy Link:**

**Current Code (Line 763):**
```html
<li>
    <a href="#" class="text-gray-400 hover:text-white smooth-transition text-sm">
        Privacy Policy
    </a>
</li>
```

**Updated Code:**
```html
<li>
    <a href="privacy.html" class="text-gray-400 hover:text-white smooth-transition text-sm">
        Privacy Policy
    </a>
</li>
```

**Find and Update Footer Terms Link:**

**Current Code (Line 765):**
```html
<li>
    <a href="#" class="text-gray-400 hover:text-white smooth-transition text-sm">
        Terms & Conditions
    </a>
</li>
```

**Updated Code:**
```html
<li>
    <a href="terms.html" class="text-gray-400 hover:text-white smooth-transition text-sm">
        Terms & Conditions
    </a>
</li>
```

**Find and Update Bottom Footer Privacy Link:**

**Current Code (Line 800):**
```html
<a href="#" class="text-sm text-gray-400 hover:text-white smooth-transition">
    Privacy Policy
</a>
```

**Updated Code:**
```html
<a href="privacy.html" class="text-sm text-gray-400 hover:text-white smooth-transition">
    Privacy Policy
</a>
```

**Find and Update Bottom Footer Terms Link:**

**Current Code (Line 804):**
```html
<a href="#" class="text-sm text-gray-400 hover:text-white smooth-transition">
    Terms of Service
</a>
```

**Updated Code:**
```html
<a href="terms.html" class="text-sm text-gray-400 hover:text-white smooth-transition">
    Terms of Service
</a>
```

---

### Using Find & Replace for Policy Links

**To update all policy links at once:**

1. **Open Find & Replace** (Ctrl+H or Cmd+H)

2. **First Replacement:**
   - Find: `href="#"` followed by text containing "Privacy"
   - Replace with: `href="privacy.html"`

3. **Second Replacement:**
   - Find: `href="#"` followed by text containing "Terms"
   - Replace with: `href="terms.html"`

---

### Step 4: Customize Policy Pages

The policy pages we created are templates. You should customize them with:

1. **Your Company Information:**
   - Replace `Photography Is Us` with your company name
   - Replace `admin@led.com` with your email
   - Replace `+1 (234) 567-890` with your phone
   - Replace `123 Photography Lane, Creative City, CC 12345` with your address

2. **Your Specific Policies:**
   - Update the content to match your actual business practices
   - Add or remove sections as needed
   - Update the "Last Updated" date

3. **Legal Requirements:**
   - Consult with a lawyer to ensure compliance with local laws
   - Consider GDPR, CCPA, and other privacy regulations
   - Include information about data processing and third-party services

---

### Verifying the Links Work

**After making all changes:**

1. **Save all three files** (`index.html`, `privacy.html`, `terms.html`)
2. **Open `index.html` in your browser**
3. **Scroll to the footer**
4. **Click on "Privacy Policy"** - should go to privacy.html
5. **Click on "Terms & Conditions"** - should go to terms.html
6. **Click on company logo or "Home"** - should return to index.html

If links don't work:
- Check file names are exactly: `privacy.html` and `terms.html`
- Make sure all three files are in the same folder
- Clear browser cache (Ctrl+Shift+Delete) and reload

---

## Troubleshooting Guide

### Common Issues and Solutions

---

### Issue 1: Links Not Working

**Problem:** Clicking a link does nothing or shows an error

**Causes and Solutions:**

1