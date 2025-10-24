# Trello Description Preview Power-Up

A custom Trello Power-Up that displays card descriptions directly on card fronts as badges.

## Features
- Show 1-5 lines of card descriptions on cards
- Customizable per board
- Settings accessible via Power-Up menu
- Works for entire team once installed

## Setup Instructions

### Step 1: Host Your Files

You need to host these files on a public HTTPS server. Here are free options:

#### Option A: GitHub Pages (Recommended)
1. Create a new GitHub repository
2. Upload all files (manifest.json, index.html, settings.html)
3. Go to repository Settings > Pages
4. Enable GitHub Pages from main branch
5. Your URL will be: `https://[username].github.io/[repo-name]/`

#### Option B: Netlify
1. Sign up at netlify.com
2. Drag and drop the folder
3. Get your URL (e.g., `https://[site-name].netlify.app/`)

#### Option C: Glitch
1. Go to glitch.com
2. Create a new project
3. Upload files
4. Your URL will be: `https://[project-name].glitch.me/`

### Step 2: Create the Power-Up in Trello

1. Go to: https://trello.com/power-ups/admin
2. Click "New Power-Up" or "Create a Power-Up"
3. Fill in the form:
   - **Name**: Description Preview
   - **Workspace**: Select your team workspace
   - **Iframe connector URL**: `https://[your-hosted-url]/index.html`
   - **Supported locales**: en (or your preference)
4. Under "Capabilities", the manifest will auto-configure:
   - card-badges ✓
   - show-settings ✓
5. Save your Power-Up

### Step 3: Add to Your Board

1. Open any Trello board in your workspace
2. Click "Power-Ups" in the menu
3. Find your "Description Preview" power-up
4. Click "Add"
5. Click "Settings" (gear icon) next to the Power-Up
6. Choose how many lines to display (1-5)
7. Save!

## How It Works

Once installed:
- Cards with descriptions will show a blue badge with the first N lines
- Click the gear icon next to the Power-Up name to adjust line count
- Settings apply to the entire board for all team members
- Long descriptions are automatically truncated

## Customization

### Change the Default Line Count
Edit `index.html` and `settings.html`, change:
```javascript
var DEFAULT_LINES = 2;
```

### Change Badge Color
In `index.html`, find the card-badges section and change:
```javascript
color: 'blue'  // Options: 'blue', 'green', 'orange', 'red', 'purple', 'pink', 'sky', 'lime', 'black'
```

### Adjust Character Limit
In `index.html`, find:
```javascript
if (preview.length > 100) {
  preview = preview.substring(0, 97) + '...';
}
```
Change 100 and 97 to your preferred limits.

## Troubleshooting

**Power-Up not showing:**
- Make sure files are on HTTPS (not HTTP)
- Check browser console for errors
- Verify the iframe connector URL is correct

**Settings not saving:**
- Refresh the board
- Check that you have board admin permissions

**Descriptions not appearing:**
- Verify cards actually have descriptions
- Check the line count setting isn't set too low
- Try refreshing the board

## Files Included

- `manifest.json` - Power-Up configuration
- `index.html` - Main Power-Up logic
- `settings.html` - Settings popup UI
- `README.md` - This file

## Support

For Trello Power-Up documentation: https://developer.atlassian.com/cloud/trello/power-ups/

## License

Free to use and modify for your team!
