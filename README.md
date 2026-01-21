# Līva Drauga Portfolio

A dynamic portfolio website with an admin panel for content management.

## Features

- **Dynamic Content**: All text and images are loaded from a central data file
- **Admin Panel**: Edit homepage text and manage gallery images
- **Authentication**: Password-protected admin access
- **Responsive Design**: Works on all devices
- **Image Galleries**: Photography, illustrations, and work showcases

## Admin Panel Features

The admin panel (`admin/admin.html`) allows you to:

1. **Edit Homepage Text**: Change the hero/main text and subtitle
2. **Upload Images from Local Files**: Upload images directly from your computer for each gallery:
   - Recent Work gallery (homepage) - **sorted by most recent first**
   - Photography gallery - **sorted by most recent first**
   - Work gallery - **sorted by most recent first**
3. **Manage Gallery Images**: Edit alt text and remove images

**Image Upload Notes**:
- Supported formats: JPG, PNG, GIF, WebP, SVG
- Maximum file size: 5MB per image
- Images are stored as data URLs in the browser (no server required)
- Uploaded images persist in browser localStorage until cleared

**Authentication**:
- Password-protected access to prevent unauthorized changes
- Session expires after 24 hours for security
- Default password: `admin2024` (change this in the code)

## Changing the Admin Password

To change the admin password, edit the `admin/admin.html` file and find this line:

```javascript
const ADMIN_PASSWORD = 'admin2024'; // Change this to your desired password
```

Replace `'admin2024'` with your desired password.

## How to Use

### Running the Website

1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the development server:
   ```bash
   npm start
   ```

3. Open your browser to `http://localhost:3000`

### Using the Admin Panel

1. Navigate to `http://localhost:3000/admin/admin.html`
2. Enter the admin password when prompted
3. Edit the homepage text in the text areas
4. For galleries:
   - Click "Choose File" in any gallery section
   - Select an image from your computer
   - Add a description (optional)
   - The image uploads automatically and appears in the gallery
5. Click "Save All Changes" to persist your edits
6. Click "Logout" when finished

## File Structure

```
kodi/
├── index.html          # Homepage
├── about.html          # About page
├── work.html           # Work gallery
├── photography.html    # Photography gallery
├── contact.html        # Contact page
├── data.json           # Content data (text and image lists)
├── style.css           # Main stylesheet
├── admin/
│   └── admin.html      # Admin panel (password protected)
└── images/             # Image assets
```

## Technical Notes

- Content is stored in `data.json` and loaded dynamically via JavaScript
- Admin changes are saved to localStorage for immediate preview
- Authentication uses sessionStorage with 24-hour expiration
- For production, you would need a backend server to persist changes to `data.json`
- Images should be placed in the `../images/` directory

## Adding New Images

1. Upload images to the `images/` folder
2. Use the admin panel to add them to galleries
3. Image paths should be relative: `../images/your-image.jpg`