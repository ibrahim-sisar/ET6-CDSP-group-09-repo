# Atmosfear - PM₂.₅ Research Website

An interactive website showcasing research on the impact of PM₂.₅ air pollution on global health.

## How to Edit Content

All website content is in the `index.html` file. You can edit any text by:

1. Opening `index.html` in any text editor
2. Finding the text you want to change
3. Editing it directly
4. Saving the file

### Common Sections to Edit:

**Hero Section:**
- Look for: `<h1>Air Pollution:<br><span class="highlight">The Invisible Killer</span></h1>`
- Change the title text as needed

**Personal Story:**
- Find: `Her mother, who has asthma, experiences severe discomfort...`
- Replace with your own story or update the existing one

**Research Question:**
- Search for: `To what extent have ambient PM₂.₅ concentrations...`
- Update with your specific research question

**Team Information:**
- Find: `Atmosfear Team` section
- Add your team member names and details

**Data Sources:**
- Update the data sources in the "About" section
- Modify GitHub repository links

## How to Host on GitHub Pages

1. **Create a new GitHub repository:**
   - Go to GitHub.com and create a new repository
   - Name it something like `pm25-research-website`

2. **Upload files:**
   - Upload all files from this folder to your repository
   - Make sure `index.html` is in the root directory

3. **Enable GitHub Pages:**
   - Go to your repository Settings
   - Scroll down to "Pages" section
   - Under "Source", select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder
   - Click "Save"

4. **Access your website:**
   - GitHub will provide a URL like: `https://yourusername.github.io/pm25-research-website`
   - It may take a few minutes to become available

## Files Included

- `index.html` - Main website file
- `girl-mask-hero.png` - Hero section background image
- `pm25-body-diagram.jpg` - Particle size penetration diagram
- `pm25-impact-body.jpg` - Systemic health effects diagram
- `pm25-respiratory.jpg` - Respiratory system impact diagram
- Other supporting images

## Customization Tips

- **Colors:** Search for color codes like `#3b82f6` (blue) in the CSS to change the color scheme
- **Fonts:** Modify the `font-family` properties in the CSS
- **Images:** Replace image files with your own (keep the same filenames)
- **Data:** Update the `sampleDALYData` object in the JavaScript section with your real data

## Adding Your Real Dataset

To integrate your actual PM₂.₅ and DALY data:

1. Find the `sampleDALYData` object in the JavaScript section
2. Replace it with your real data in the same format:
```javascript
const realDALYData = {
    'Country Name': { 2010: value1, 2011: value2, ... },
    // Add all your countries and years
};
```

## Support

For any questions about editing or hosting, refer to:
- GitHub Pages documentation: https://pages.github.com/
- HTML/CSS tutorials for more advanced customization

