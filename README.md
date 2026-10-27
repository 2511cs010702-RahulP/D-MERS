# D-MERS — Disaster Management & Emergency Response System

"One Platform. Faster Response. Safer Communities."

---

## For Developer

This section contains technical information for maintaining, building, and deploying the D-MERS application.

### Technology Stack
- **Frontend**: React 18, TypeScript, Vite, Tailwind CSS, Lucide Icons
- **Backend**: Supabase (PostgreSQL, Auth, Storage)
- **Desktop Wrapper**: Electron, electron-builder (for Windows installer)

### Supabase Setup
1. Create a new Supabase project.
2. Run the SQL script found in `supabase/schema.sql` in the Supabase SQL Editor. This will set up the tables, RLS policies, triggers, and insert demo seed data.
3. Obtain your Project URL and anon key.

### Environment Variables
Create a `.env` file in the root directory (use `.env.example` as a template):
```env
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```
*Note: Never commit your real `.env` file containing sensitive credentials to version control.*

### Local Development
To run the application in a local web development environment:
```bash
npm install
npm run dev
```

To run the application in the local Electron development environment:
```bash
npm run electron:dev
```

### Production Build & Windows Packaging
To generate the final Windows installer (`.exe`):
```bash
npm run package:windows
```
This command will:
1. Build the production React assets into the `dist/` directory.
2. Package the Electron app using `electron-builder`.
3. Output the installer in the `release/` directory (e.g., `release/D-MERS Setup 1.0.0.exe`).

### Application Architecture
- **Web App**: Hosted in `src/` and built using Vite.
- **Desktop App**: `desktop/main.cjs` acts as the Electron entry point, loading the Vite build and managing the native application lifecycle.
- **Icons**: Icons are dynamically generated using `desktop/create-icons.ps1`.

---

## For Normal User

Welcome to D-MERS, your centralized disaster management and emergency response platform.

### Installation Instructions

1. **Download the Installer**: Locate the `D-MERS-Setup.exe` file (or similar named installer).
2. **Install**: Double-click the installer and follow the on-screen prompts.
3. **Desktop Shortcut**: Ensure the "Create Desktop Shortcut" option is selected during installation.
4. **Launch**: Double-click the D-MERS icon on your Desktop or Start Menu to open the application.
5. **Sign In**: Click "Sign In" and authenticate securely using your Google Account or Email.
6. **Use the Application**: You are now ready to report emergencies, coordinate rescues, or access resources!

*Note: D-MERS requires an active internet connection to synchronize with the emergency response network.*
