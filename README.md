🧩 MatricLink

Bridging learners, educators, and opportunities through an accessible digital platform.

MatricLink is a cross-platform educational application built with .NET MAUI (Multi-platform App UI) and Blazor Hybrid, combining native performance with modern web technologies (HTML, CSS, JavaScript).
The app connects seamlessly to the MatricLinkWebsite repository hosted on Vercel, enabling consistent web and mobile experiences from a unified codebase.

📱 Overview

MatricLink provides learners with access to educational resources, user profiles, sign-up and login functionality, and integrated data management — all through an elegant, responsive interface.
The app runs offline and online, synchronizing data with the hosted web version whenever internet access is available.

⚙️ Core Technologies
Layer	Technology	Purpose
Frontend	HTML, CSS, JavaScript	UI/UX and interactive components
App Framework	.NET MAUI + Blazor Hybrid	Cross-platform native app structure
Language	C#	Backend logic, data handling, and API interop
Hosting	Vercel	Front-end deployment and continuous delivery
Source Control	Git & Git Submodules	Unified versioning of app and front-end
Database	(Planned) SQLite / Azure SQL	User data and state persistence
🧠 Architecture

MatricLink is structured around a hybrid architecture where the frontend repository (hosted on Vercel) is added as a Git submodule inside the MAUI project.

MatricLink/
│
├── MatricLink/                     # MAUI app root
│   ├── wwwroot/                    # Local web assets (mirrors hosted site)
│   ├── Components/                 # Blazor/MAUI hybrid UI components
│   ├── Platforms/                  # Platform-specific code (Android, iOS, Windows)
│   ├── Resources/                  # Fonts, images, splash screens
│   ├── App.xaml / App.xaml.cs      # Core app configuration
│   ├── MainPage.xaml / .cs         # Main interface with WebView
│   └── MauiProgram.cs              # Dependency injection and service setup
│
└── MatricLinkWebsite/              # Git submodule (Vercel-hosted frontend)
    ├── index.html
    ├── css/
    ├── js/
    └── assets/

Hybrid Loading Logic
#if DEBUG
    webView.Source = "https://matriclink.vercel.app";  // Remote (online)
#else
    webView.Source = "wwwroot/app/index.html";          // Local (offline)
#endif


Debug Mode: Loads the hosted site from Vercel for live testing.

Release Mode: Loads the local wwwroot copy for offline or deployed app use.

🧩 JavaScript & Interop

Each HTML page (e.g., Signup, Login, Profile) uses its own dedicated JS file for modularity during development:

js/
 ├─ signup.js
 ├─ login.js
 ├─ profile.js
 └─ utils.js


These can later be bundled into one optimized file for production.
C# and JavaScript communicate through JS Interop, allowing backend logic to handle authentication, data persistence, and API requests.

🔄 Data & Backend Integration

Planned backend stack (C#):

SQLite or Azure SQL for storing user data locally or in the cloud.

Entity Framework Core for ORM-based database access.

HttpClient for API calls between C# and hosted services (e.g., REST endpoints).

This enables offline-first data handling — syncing automatically when the user reconnects.

💻 Cross-Platform Compatibility

MatricLink runs seamlessly across:

Windows (desktop)

Android (mobile and tablet)

iOS, MacCatalyst, and Tizen (future expansion)

Responsive layout ensures consistent UI across varying screen sizes and resolutions.

🚀 Deployment
Environment	Description	Access
🌐 Web	Hosted version of the app frontend	matriclink.vercel.app

📱 Mobile/Desktop	MAUI-built native app	Distributed via app stores or installer packages
🧭 Development Workflow
1. Clone Main Repository
git clone https://github.com/YourUser/MatricLink.git

2. Initialize Submodule (Frontend)
git submodule add https://github.com/SakhileKhuzwayo222/MatricLinkWebsite.git
git submodule update --init --recursive

3. Run in Debug Mode
dotnet build
dotnet run

4. Publish for Release
dotnet publish -c Release

🧩 Future Plans

🔐 Secure authentication & user roles

☁️ Cloud synchronization between mobile and web

🧠 AI-assisted learning recommendations

💬 In-app messaging & resource sharing

📄 License

This project is licensed under the MIT License.
See LICENSE
 for details.

👨‍💻 Author

Sakhumuzi Khuzwayo
Software Developer | Structuralist | Son of Venus
🌐 linktr.ee/sakhil.e
