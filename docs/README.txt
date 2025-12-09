HOSTEL ROOM ALLOCATION & MAINTENANCE
CLICKABLE PROTOTYPE (CODE-FIRST) - HOW TO USE & EXPLAIN

What this is
- A simple HTML/CSS prototype (no backend) to demo 3 flows:
  1) Student requests a room and checks status
  2) Staff allocates a room to a student
  3) Student submits a maintenance request; Staff updates work orders

How to open
- Open prototype/index.html in any modern browser (Chrome/Edge/Firefox).
- There is no server needed; files are static.

Structure
- index.html                  → fake “login” to choose role
- styles.css                  → shared styles
- student/dashboard.html      → student home
- student/request-room.html   → room request form
- student/request-status.html → status with pending/allocated/error
- student/maintenance.html    → maintenance request form
- staff/dashboard.html        → staff home
- staff/allocate-room.html    → allocate rooms (simulated)
- staff/work-orders.html      → update maintenance tickets

How to demo (script)
1) Login as Student → Start Room Request → fill and submit
   - You’ll land on “My Status” with Pending state.
2) Switch to Staff → Allocate Room → click Allocate for a student
   - This simulates success and opens Student Status with Allocated.
3) Student → Maintenance → submit a new ticket
   - Staff → Work Orders → change status from Open → In Progress → Done.

What’s real vs fake
- Real: navigation, UI components, clickable flows, success/error states.
- Fake: authentication, data storage, policies, and backend logic.

Why code-first
- Faster than high-fidelity design for small teams.
- Stakeholders see something that feels like the final app.
- Easy to extend later into a real app.

Talking points for peers
- Roles: we simulate Student and Staff without real login.
- Room Allocation flow: request → staff assigns → student sees status.
- Maintenance flow: student opens ticket → staff updates → student sees progress (demo via staff page).
- Constraints: prototype only; no database or security yet.

Common questions
- Can this be mobile? Yes, but we focused on desktop for speed.
- Can we integrate real data? Later; this phase is for validation only.
- Is this the final UI? It’s a baseline; we can polish after feedback.

END

