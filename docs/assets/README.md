# Assets Directory

This directory contains all media assets for the course website.

## Directory Structure

```
assets/
├── staff/          # Photos of course instructors and TAs
├── speakers/       # Photos of guest speakers
└── slides/         # Lecture slides and presentation materials
```

## Image Guidelines

### Staff and Speaker Photos

- **Format**: JPG or PNG
- **Size**: Recommended 400x400px minimum (square aspect ratio)
- **File naming**: Use lowercase with hyphens (e.g., `john-doe.jpg`)
- **Optimization**: Compress images to keep file sizes under 200KB

### Example File Names

```
assets/staff/professor-smith.jpg
assets/speakers/jane-doe.png
assets/slides/lecture-01.pdf
```

## Adding Images to the Website

### For Staff Photos

1. Add image to `assets/staff/`
2. Update `index.html` in the staff section:

```html
<div class="staff-card">
    <img src="assets/staff/professor-name.jpg" alt="Professor Name" 
         style="width: 180px; height: 180px; border-radius: 50%; object-fit: cover; margin-bottom: 1.25rem; box-shadow: var(--shadow-md);">
    <h3 class="staff-name">Professor Name</h3>
    <p class="staff-title">Title, Institution</p>
    <a href="#" class="staff-link">Website</a>
</div>
```

### For Speaker Photos

1. Add image to `assets/speakers/`
2. Update `index.html` in the speakers section:

```html
<div class="speaker-card">
    <img src="assets/speakers/speaker-name.jpg" alt="Speaker Name"
         style="width: 120px; height: 120px; border-radius: 50%; object-fit: cover; margin-bottom: 1rem; box-shadow: var(--shadow-sm);">
    <h4 class="speaker-name">Speaker Name</h4>
    <p class="speaker-title">Title</p>
    <p class="speaker-org">Organization</p>
</div>
```

## Image Optimization Tools

- [TinyPNG](https://tinypng.com/) - Compress PNG/JPG images
- [Squoosh](https://squoosh.app/) - Advanced image optimization
- [ImageOptim](https://imageoptim.com/) - Mac app for compression

## Tips

1. **Always use descriptive alt text** for accessibility
2. **Optimize images before uploading** to keep the site fast
3. **Use consistent dimensions** for a professional look
4. **Keep file names lowercase** with hyphens for better compatibility
