# Brave-Backgrounds
The backgrounds brave uses

We used the inspect console command 
```(() => {
  // Try common elements that hold background images
  const elements = document.querySelectorAll('*');

  for (const el of elements) {
    const bg = getComputedStyle(el).backgroundImage;
    if (bg && bg !== 'none' && bg.includes('url(')) {
      const url = bg.match(/url\(["']?(.*?)["']?\)/)?.[1];
      if (url) {
        const a = document.createElement('a');
        a.href = url;
        a.download = 'brave-background.jpg';
        document.body.appendChild(a);
        a.click();
        a.remove();
        console.log('Downloaded:', url);
        return;
      }
    }
  }

  console.log('No background image found.');
})();
```
