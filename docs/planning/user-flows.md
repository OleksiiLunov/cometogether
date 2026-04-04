# User Flows

## Overview
This document outlines the core user flows based on the user story map.
The platform has a single user type (Musician), who can create and manage Bands.

---

# Musician Core Flows

## 1. Sign Up

**User:** Musician  
**Goal:** Create an account and access the platform  

### Flow:
1. User opens the website
2. User clicks "Sign Up"
3. User chooses sign-up method:
   - Email & password
   - (optional, MVP+) Social login (Google, etc.)
4. User enters required information:
   - Email
   - Password
5. User submits the registration form
6. System validates input:
   - Email format is correct
   - Password meets requirements
7. System checks if user already exists
8. If validation fails:
   - System shows error message
   - User corrects input
9. If validation succeeds:
   - System creates a new user account
10. (Optional, MVP decision) System sends email verification
11. User is redirected to:
   - Profile creation page

---

## 2. Log In

**User:** Musician  
**Goal:** Access their existing account  

### Flow:
1. User opens the website
2. User clicks "Log In"
3. System displays login form
4. User enters credentials:
   - Email
   - Password
5. User submits the form
6. System validates input format
7. System attempts to authenticate user
8. If authentication fails:
   - System shows error message ("Invalid email or password")
   - User retries login
9. If authentication succeeds:
   - System creates user session
10. System redirects user to:
    - Dashboard

---

## 3. Create Musician Profile

**User:** Musician  
**Goal:** Create a profile to present themselves and be discoverable  

### Flow:
1. User is redirected to profile creation after sign up (or navigates manually)
2. System shows profile creation form
3. User enters basic information:
   - Display name
   - Location
4. User adds musical information:
   - Instrument(s)
   - Genre(s)
   - Skill level / experience
5. User adds optional details:
   - Bio / description
   - Links (YouTube, Spotify, etc.)
6. User uploads profile picture (optional for MVP)
7. User submits the profile form
8. System validates required fields
9. If validation fails:
   - System shows error messages
   - User corrects input
10. If validation succeeds:
   - System saves profile data
11. System redirects user to:
   - Dashboard

---

## 4. Manage Profile

**User:** Musician  
**Goal:** Update and maintain personal profile information  

### Flow:
1. User logs into the system
2. User navigates to profile section:
   - via profile icon/menu
   - or "Edit Profile" button
3. System displays current profile data
4. User edits one or more fields:
   - Display name
   - Location
   - Instruments
   - Genres
   - Experience level
   - Bio / description
   - Links (YouTube, Spotify, etc.)
5. User updates profile picture (optional)
6. User submits changes
7. System validates updated data
8. If validation fails:
   - System shows error messages
   - User corrects input
9. If validation succeeds:
   - System saves updated profile
10. System shows confirmation (e.g., "Profile updated successfully")
11. User continues using the platform
---

# Band Management Flows

## 5. Create Band

**User:** Musician (Owner)  
**Goal:** Create a new band and start building a group  

### Flow:
1. User logs into the system
2. User navigates to band-related section:
   - "My Bands" / "Create Band"
3. User clicks "Create Band"
4. System displays band creation form
5. User enters basic band information:
   - Band name
   - Location
6. User adds musical details:
   - Genre(s)
   - Description / bio
7. User defines band needs (optional for MVP):
   - Looking for instruments (e.g., drummer, bassist)
8. User uploads band image (optional)
9. User submits the form
10. System validates required fields
11. If validation fails:
    - System shows error messages
    - User corrects input
12. If validation succeeds:
    - System creates a new band
    - System assigns user as band owner
13. System redirects user to:
    - Band profile page

---

## 6. Manage Band Profile

**User:** Musician (Band Owner / Member with permissions)  
**Goal:** Update and maintain band information  

### Flow:
1. User logs into the system  
2. User navigates to "My Bands"  
3. User selects a specific band  
4. System displays band profile page  
5. System checks if user has permission to edit the band  
6. If user does NOT have permission:
   - System hides "Edit Band Profile" button  
   - User can only view band profile  
7. If user has permission:
   - System displays "Edit Band Profile" button  
   - User clicks "Edit Band Profile"  
   - System displays editable form with current band data  
8. User updates one or more fields:
   - Band name  
   - Location  
   - Genre(s)  
   - Description / bio  
   - "Looking for" instruments (optional)  
9. User updates band image (optional)  
10. User submits changes  
11. System validates updated data  
12. If validation fails:
    - System shows error messages  
    - User corrects input  
13. If validation succeeds:
    - System saves updated band data  
14. System shows confirmation (e.g., "Band profile updated successfully")

15. User continues managing the band  

---

## 7. Invite Musicians to Band

**User:** Musician (Band Owner)  
**Goal:** Invite other musicians to join the band  

### Flow:
1. User logs into the system  
2. User navigates to "My Bands"  
3. User selects a specific band  
4. System displays band profile page  
5. System checks if user has permission to manage members  
6. If user does NOT have permission:
   - System hides "Invite Musician" option  
   - User can only view members  
7. If user has permission:
   - User opens "Members" or "Manage Members" section  
   - User clicks "Invite Musician"  
   - System provides invitation options:
     - Search for musicians (by filters)
     - OR enter username/email (optional for MVP)  
8. User searches for musicians:
   - by instrument  
   - genre  
   - location (optional)  
9. System displays list of matching musicians  
10. User selects a musician  
11. User clicks "Invite"  
12. (Optional) User adds a message  
13. System sends invitation to selected musician  
14. System creates invitation record (status: pending)  
15. System shows confirmation (e.g., "Invitation sent")  
16. Invited musician receives notification  

---

## 8. Accept / Reject Band Invitation

**User:** Musician  
**Goal:** Decide whether to join a band  

### Flow:
1. Musician logs into the system
2. Musician navigates to "Notifications" / "Invitations"
3. System displays list of pending band invitations
4. Musician selects a specific invitation
5. System shows band details:
   - Name
   - Genre(s)
   - Owner
   - Current members
6. Musician chooses action:
   - Accept
   - Reject
7. If musician accepts:
   - System updates band membership
   - Musician becomes band member
   - System notifies band owner
8. If musician rejects:
   - System marks invitation as declined
   - System notifies band owner
9. System confirms action to musician

---

## 9. Leave Band

User: Musician  
Goal: Leave a band they are a member of

### Flow:

1. User navigates to the band profile page
2. System displays band information, member list, and available actions
3. User clicks "Leave Band" button
4. System checks:
   - If user is **last admin** or **only member**, system shows modal:  
     "You are the last admin. Leaving will delete the band. Are you sure?"  
     - User can **confirm** → proceed to step 6  
     - User can **cancel** → stop flow
   - Else, system shows confirmation modal with:
     * Warning about losing access to band content
     * Optional feedback field for reason of leaving
5. User confirms leaving
6. System:
   * Removes user from band member list
   * If user was last admin / only member, deletes the band and removes all members
   * Updates band dashboard
   * Sends optional notification to band admin
7. System shows success message: "You have left the band"
8. User is redirected to personal dashboard or bands list

---

# Discovery Flows

## 10. Search for Bands

User: Musician  
Goal: Find new bands to join or explore

### Flow:

1. User navigates to the "Bands" search page or uses search bar from dashboard
2. System displays search interface with:
   - Search field (keywords, genre, location)
   - Filters (skill level, band type, online/offline, availability)
   - Sort options (relevance, newest, popularity)
3. User enters search query and applies filters
4. System displays list of bands matching criteria
5. User can:
   - Click on a band to view profile
   - Bookmark/save band for later
   - Apply to join the band (if allowed)
6. User views band profile
7. System shows band details:
   - Name, genre, description
   - Member list
   - Upcoming events or rehearsals
   - Join/apply button (if user is not already a member)
8. User decides to:
   - Apply to join → system sends application/notification to band admin
   - Go back to search results → system retains search filters and query
   - Close search → return to dashboard

### Notes:

- Search results update dynamically as filters are applied
- System may suggest bands based on user profile and past activity
- If no results match, system shows “No bands found” with option to reset filters

---

## 11. View Band Profile

User: Musician  
Goal: See detailed information about a band

### Flow:

1. User navigates to a band profile from:
   - Search results
   - Dashboard (saved/bookmarked bands)
   - Notifications or invitations
2. System displays band profile page with:
   - Band name, genre, and description
   - Member list with roles and instruments
   - Upcoming events, rehearsals, or gigs
   - Media: photos, videos, audio samples
   - Join/Apply button (if user is not already a member)
   - Message or contact button (if allowed)
3. User can:
   - View full member details
   - Listen to or watch media
   - Send message to band admin or members
   - Apply to join the band (if applicable)
   - Bookmark/save the band for later
4. System handles interactions:
   - Displays messaging interface or modal
   - Sends application to band admin if user applies
   - Confirms successful bookmark/save
5. User decides next action:
   - Return to search results or dashboard
   - Continue browsing band content
   - Exit band profile

---

## 12. Search for Musicians

User: Musician  
Goal: Find other musicians to collaborate with or join a band

### Flow:

1. User navigates to the "Musicians" search page or uses search bar from dashboard
2. System displays search interface with:
   - Search field (keywords, instrument, genre, location)
   - Filters (skill level, availability, online/offline, experience)
   - Sort options (relevance, newest, popularity)
3. User enters search query and applies filters
4. System displays list of musicians matching criteria
5. User can:
   - Click on a musician to view their profile
   - Send connection request or message
   - Bookmark/save musician for later
6. User views musician profile
7. System shows musician details:
   - Name, instruments, skill level
   - Genres and styles
   - Availability and location
   - Bands they are part of (if public)
   - Media: recordings, videos, or samples
   - Message or contact button
8. User decides to:
   - Send a message or collaboration request → system sends notification
   - Bookmark/save musician → system confirms save
   - Return to search results → system retains search filters
   - Close search → return to dashboard

### Notes:

- Search results update dynamically as filters are applied
- System may suggest musicians based on user profile and past activity
- If no results match, system shows “No musicians found” with option to reset filters
---

## 13. View Musician Profile

User: Musician  
Goal: See detailed information about another musician

### Flow:

1. User navigates to a musician profile from:
   - Search results
   - Dashboard (saved/bookmarked musicians)
   - Notifications or invitations
2. System displays musician profile page with:
   - Name, instruments, and skill level
   - Genres and styles
   - Location and availability
   - Bands they are part of (if public)
   - Media: recordings, videos, or samples
   - Message or contact button
   - Bookmark/save button
3. User can:
   - View full musician details
   - Listen to or watch media
   - Send a message or collaboration request
   - Apply to invite musician to a band (if user is band admin)
   - Bookmark/save musician for later
4. System handles interactions:
   - Displays messaging interface or modal
   - Sends collaboration request or invitation if applicable
   - Confirms successful bookmark/save
5. User decides next action:
   - Return to search results or dashboard
   - Continue browsing musician content
   - Exit musician profile

---

# Interaction Flows

## 14. Send Join Request to Band

User: Musician  
Goal: Request to join a band

### Flow:

1. User navigates to a band profile from:
   - Search results
   - Dashboard (saved/bookmarked bands)
   - Notifications or invitations
2. System displays band profile with:
   - Band name, genre, description
   - Member list
   - Join/Apply button
3. User clicks “Join Band” or “Apply” button
4. System displays join request modal:
   - Optional message/cover note field
   - Confirm or cancel buttons
5. User fills optional message and confirms request
6. System:
   - Sends join request notification to band admin(s)
   - Confirms to user: “Your request has been sent”
7. User decides next action:
   - Return to search results or dashboard
   - View other bands
   - Close band profile

---

## 15. Review Join Requests

User: Band Admin  
Goal: Review and respond to incoming join requests from musicians

### Flow:

1. Admin navigates to the band dashboard or notifications
2. System displays list of pending join requests with:
   - Requesting musician name
   - Instruments, skill level, genres
   - Optional message/cover note
   - Date of request
3. Admin selects a join request to review
4. System displays detailed request information and options:
   - Approve / Accept
   - Reject / Decline
   - Message musician (optional)
5. Admin takes action:
   - Approve:
     - System adds musician to band member list
     - Sends confirmation notification to musician
   - Reject:
     - System sends rejection notification to musician
   - Optional: Admin sends custom message to musician
6. Admin decides next action:
   - Review next pending request
   - Return to band dashboard
   - Exit notifications
---

## 16. Messaging

User: Musician  
Goal: Send and receive messages with other musicians or bands in a single conversation thread

### Flow:

1. User navigates to the messaging interface from:
   - Dashboard
   - Notifications
   - Musician or Band profile
2. System displays inbox with:
   - List of existing conversations (one per musician or band)
   - Search and filter options
   - New message button
3. User selects an existing conversation or clicks “New Message”
4. System displays a single conversation thread with the selected musician or band:
   - Shows full message history in chronological order
   - Text input field at the bottom
   - Optional attachments (audio, video, images)
   - Send button
5. User composes and sends a message
6. System:
   - Delivers message to recipient
   - Updates conversation thread in real-time
   - Sends notification to recipient
7. User can:
   - Reply to messages in the same thread
   - Attach additional media
   - Delete messages from their view or archive conversation
8. User decides next action:
   - Continue messaging in the same conversation
   - Return to inbox to select another conversation
   - Exit messaging interface

---

## 17. Receive Notifications

User: Musician  
Goal: Stay informed about important events, messages, and updates on the platform

### Flow:

1. System detects an event related to the user, such as:
   - New message from another musician or band
   - Join request sent to user’s band (if user is admin)
   - Invitation to join a band
   - Event or rehearsal updates in a band user is a member of
   - System announcements or updates
2. System creates a notification with:
   - Type (message, request, invitation, update)
   - Brief description or title
   - Timestamp
   - Link to relevant page (conversation, band, dashboard)
3. User sees notification via:
   - Platform inbox or notification center
   - Optional push notification (email, mobile app, browser)
4. User clicks notification
5. System redirects user to the relevant page:
   - Message → opens conversation thread
   - Join request → opens request review interface
   - Invitation → opens band profile or join request modal
   - Event/update → opens event details or dashboard
6. User takes action on notification:
   - Respond to message
   - Accept/decline join request or invitation
   - Review event details
   - Dismiss notification
7. System marks notification as read once user interacts with it or manually dismisses it
8. User decides next action:
   - Continue interacting with the content
   - Return to dashboard or other platform sections
   - Exit notifications interface
---
