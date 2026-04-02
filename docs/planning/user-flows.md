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
   - Profile creation page OR
   - Dashboard (if profile can be completed later)

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
    - Dashboard OR
    - Last visited page (if applicable)

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
   - Dashboard OR
   - Discovery (e.g., "Find Bands")

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
    - Band profile page OR
    - Band management page

---

## 6. Manage Band Profile

**User:** Musician (Band Owner / Member with permissions)  
**Goal:** Update and maintain band information  

### Flow:
1. User logs into the system
2. User navigates to "My Bands"
3. User selects a specific band
4. System displays band profile page
5. User clicks "Edit Band Profile"
6. System displays editable form with current band data
7. User updates one or more fields:
   - Band name
   - Location
   - Genre(s)
   - Description / bio
   - "Looking for" instruments (optional)
8. User updates band image (optional)
9. User submits changes
10. System validates updated data
11. If validation fails:
    - System shows error messages
    - User corrects input
12. If validation succeeds:
    - System saves updated band data
13. System shows confirmation (e.g., "Band profile updated successfully")
14. User continues managing the band

---

## 7. Invite Musicians to Band

**User:** Musician (Band Owner)  
**Goal:** Invite other musicians to join the band  

### Flow:
1. User logs into the system
2. User navigates to "My Bands"
3. User selects a specific band
4. User opens "Members" or "Manage Members" section
5. User clicks "Invite Musician"
6. System provides invitation options:
   - Search for musicians (by filters)
   - OR enter username/email (optional for MVP)
7. User searches for musicians:
   - by instrument
   - genre
   - location (optional)
8. System displays list of matching musicians
9. User selects a musician
10. User clicks "Invite"
11. (Optional) User adds a message
12. System sends invitation to selected musician
13. System shows confirmation (e.g., "Invitation sent")
14. Invited musician receives notification

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

**User:** Musician  
**Goal:** Exit band  

### Flow:
1. ...

---

# Discovery Flows

## 10. Search for Bands

**User:** Musician  
**Goal:** Find bands to join  

### Flow:
1. ...

---

## 11. View Band Profile

**User:** Musician  
**Goal:** Evaluate a band  

### Flow:
1. ...

---

## 12. Search for Musicians

**User:** Musician (Band Owner / Member)  
**Goal:** Find musicians for band  

### Flow:
1. ...

---

## 13. View Musician Profile

**User:** Musician  
**Goal:** Evaluate another musician  

### Flow:
1. ...

---

# Interaction Flows

## 14. Send Join Request to Band

**User:** Musician  
**Goal:** Apply to join a band  

### Flow:
1. ...

---

## 15. Review Join Requests

**User:** Musician (Band Owner / Member with permissions)  
**Goal:** Accept or reject candidates  

### Flow:
1. ...

---

## 16. Messaging

**User:** Musician  
**Goal:** Communicate with other users  

### Flow:
1. ...

---

## 17. Receive Notifications

**User:** Musician  
**Goal:** Stay updated on activity  

### Flow:
1. ...