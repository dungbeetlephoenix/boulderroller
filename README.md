BoulderRollers

Description:
BoulderRollers is a decentralized, gamified fitness ecosystem that rewards users for their physical activity. The app is built using SwiftUI for iOS and integrates simulated blockchain token operations via the Solana testnet. It features an E-Ink design aesthetic using a monospaced font and a high-contrast color scheme.

Features:
  - User Authentication and Management via an in-house UserManager.
  - Community Feed: A feed that displays user-uploaded rides; initially empty until workouts are recorded.
  - Live Map and Route Recording: Uses CoreLocation and MapKit to capture GPS route data.
  - Activity Recording: Records workouts in real time and calculates metrics (time, distance, speed).
  - Post-Activity Review: Allows users to review and edit ride details and simulates token rewards.
  - Modular Design: Organized into modules for Home, Map, Record, Groups, and Profile; integrated via a bottom TabView.
  - E-Ink Aesthetic: A custom design system that applies systemGray6 for backgrounds, label colors for text, and a monospaced font.

Repository Structure:
BoulderRollers/
  BoulderRollersApp.swift         (Main entry point; launches ContentView)
  Info.plist                      (App configuration; includes NSLocationWhenInUseUsageDescription)
  Assets.xcassets/                (Image assets; includes splash-logo, tab icons, etc.)
  Models/
    Ride.swift                    (Ride model including route data)
    TokenTransaction.swift        (Stub model for token transactions)
    User.swift                    (User model)
  Managers/
    WalletManager.swift           (In-house wallet creation and secure storage)
    LocationManager.swift         (CoreLocation service)
    SmartContractManager.swift    (Simulated blockchain calls)
    UserManager.swift             (User management and ride persistence)
  Services/
    DesignSystem.swift            (E-Ink design system; defines colors and fonts)
  Views/
    Loading/
      LoadingView.swift           (Splash/loading screen)
    Login/
      LoginView.swift             (User login screen)
    Home/
      HomeView.swift              (Community feed screen)
      RideCardView.swift          (Ride summary card view)
      RideDetailView.swift        (Detailed ride view)
    Map/
      MapView.swift               (Reusable MapKit view component)
      MapTabView.swift            (Map screen with search and heatmap toggle)
    Record/
      RecordTabView.swift         (Activity recording screen with route data)
      ActivityMetricsView.swift   (Live metrics overlay)
      PostActivityView.swift      (Ride finalization form)
    Groups/
      GroupsView.swift            (Stub groups screen)
    Profile/
      ProfileView.swift           (Stub user profile screen)
    MainTabView.swift             (Main bottom navigation TabView)
    ContentView.swift             (Root view: shows LoginView if not logged in; otherwise, MainTabView)

Getting Started:
  1. Clone the repository.
     Command: git clone https://github.com/yourusername/BoulderRollers.git
  2. Open the BoulderRollers.xcodeproj file in Xcode.
  3. Ensure Info.plist contains the key:
       NSLocationWhenInUseUsageDescription
     with a suitable description.
  4. Build and run the project on a simulator or device.
  5. Test the app:
       - Login: If no user is logged in, the Login screen appears.
       - Home Feed: The Home feed will initially be empty until a workout is recorded.
       - Record a Ride: Use the Record tab to capture a ride (route data is recorded via GPS).
       - Post Activity: After finishing a ride, review ride details in PostActivityView and save the ride.
       - The new ride appears in the Home feed.

Dependencies:
  - SwiftUI for UI development.
  - CoreLocation for GPS data.
  - UserDefaults for local persistence (to be replaced by a proper backend in production).
  - SF Symbols for iconography.
  - Planned future dependencies include Solana.Swift and HDWalletKit for blockchain integration and robust wallet management.

Contributing:
  - Please follow the established Git workflow for pull requests.
  - Write tests for new features and ensure backward compatibility.
  - Adhere to the E-Ink design guidelines defined in Services/DesignSystem.swift.

License:
  - This project is licensed under the MIT License.

Contact:
  - For further information, please contact the development team at dungbeetlephoenix@proton.me
