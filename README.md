MedVyavastha
Streamlining Information Flow for Emergency Medical Transit.

MedVyavastha is a healthcare management platform designed to bridge the critical information gap between ambulances and hospitals during emergency transit. By ensuring that patient data reaches the emergency room before the ambulance does, we empower medical teams to prepare life-saving interventions in advance.

🚀 Key Features

1. Real-time Transit Monitoring: Tracks emergency vehicles and updates hospital staff on estimated arrival times.
2. Pre-Arrival Patient Data: Securely transmits vital signs and medical history to the receiving hospital while the patient is still en route.
3. Dynamic Resource Allocation: Helps hospitals manage bed availability and specialized equipment based on incoming emergency data.
4. Unified Dashboard: A minimalist, high-contrast interface for medical professionals to monitor multiple incoming emergencies simultaneously.

website = https://medvyavastha.netlify.app/

👥 The Team

1. Pranshu Aryan – Lead Backend Engineer & Systems Architect Responsible for the end-to-end backend architecture, full Firebase integration, and real-time database management. Acted as the primary debugger, resolving deep-rooted UI/UX bottlenecks and ensuring seamless data flow between the hospital and transit systems.
2. Mahima Kumari – Lead Frontend Developer & Feature Specialist Headed the development of core platform features and frontend coordination. Focused on translating complex healthcare workflows into functional user interfaces and ensuring cross-component compatibility throughout the development sprint.

🛠️ Challenges We Faced

1. Real-time Data Synchronization Bugs
The Problem: Initially, there was a significant lag when syncing patient vitals between the ambulance and the hospital dashboard, leading to outdated information.

The Fix: We optimized our Firebase Firestore listeners and implemented local state management to ensure the UI updates instantly without waiting for full database round-trips.

2. PptxGenJS Integration Hurdles
The Problem: Generating automated medical reports in PPT format caused memory leaks in the browser during the conversion of complex data tables.

The Fix: We refactored the data-parsing logic to handle information in smaller chunks, ensuring smooth document generation even on low-end devices.

3. IoT Connectivity Stabilities
The Problem: Maintaining a constant connection for transit monitoring in low-network areas (common during medical emergencies) caused the application to crash.

The Fix: We implemented a "Sync-when-Online" architecture using Firebase’s offline persistence features, allowing the app to store data locally and upload it the moment a connection is restored.

🛠️ The Debugging Journey (here is the one of the challenges we faced)

Building MedVyavastha was a race against time, and our team (Pranshu Aryan and Mahima Kumari) spent hours navigating a "domino effect" of technical hurdles on the FindHospital page:

1. The "Ghost" UI (Unclickable Elements)
The Problem: Initially, every element on the FindHospital page was unresponsive. Buttons and search bars were visible but impossible to click.

The Fix: We discovered a Z-index conflict where an invisible overlay was capturing all click events. Adjusting the CSS layering restored interactivity.

2. The Search-to-Box Breakdown
The Problem: Once the page was clickable, the search functionality broke. Even when searching for a hospital, the result boxes refused to open or expand.

The Fix: We refactored our state logic. The search query wasn't correctly triggering the toggle state for the hospital detail components.

3. The "Blur & Drift" UI Crisis
The Problem: After fixing the search, the page was hit with two visual bugs: a permanent blur filter stayed stuck on the screen, and the hospital boxes shifted into "weird" overlapping positions.

The Fix: This was caused by a CSS class that wasn't being removed after a modal closed. We manually cleaned up the conditional rendering and reset the Flexbox positioning.

4. Real-time Firebase Integration
The Problem: Even with the UI fixed, the data was static. We needed the hospital availability to update instantly as ambulances moved.

The Fix: After hours of troubleshooting, we successfully linked the frontend to Firebase Firestore. We implemented real-time snapshots so that availability data reflects live changes without a page refresh.

### ⚖️ License & Intellectual Property
This project is proprietary. The code is public for review purposes only. No permission is granted to copy, modify, or redistribute this work.
