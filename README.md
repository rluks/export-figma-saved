# export-figma-saved
Backup Figma Community resources saved on your Figma profile

Go to your profile at https://www.figma.com/<profile>/saves
Open DevTools
Paste code to console
Paste copied JSON to new text file

// Extract all community resource links
const links = Array.from(document.querySelectorAll('a.tile_meta--title--d8E1J'))
  .map(a => ({
    title: a.textContent.trim(),
    url: 'https://www.figma.com' + a.getAttribute('href')
  }));

// Display in console
console.table(links);

// Copy as JSON to clipboard
copy(links);

console.log(`Found ${links.length} items. JSON copied to clipboard!`);
