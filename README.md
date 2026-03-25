# CampusPe — Authentication UI

A fully responsive, professional authentication system built with **Bootstrap 5**, **Bootstrap Icons**, and a custom **CSS design system**. This project demonstrates a complete multi-page auth flow with modern UI patterns, client-side form validation, and a functional student dashboard.

---

## Live Preview

> Open `login.html` directly in any browser — no server required.

---

## Screenshots

Place screenshots inside a `screenshots/` folder in the root of the repository.

| Page | File | What to capture |
|---|---|---|
| Login | `screenshots/login.png` | Centered card on dark gradient background, email + password fields, Sign In button |
| Login (mobile) | `screenshots/login-mobile.png` | Same page at 375px width — card fills screen with compact padding |
| Register | `screenshots/register.png` | 4-field form with password strength bar visible (type a weak password first) |
| Register (validation) | `screenshots/register-validation.png` | Submit with empty fields to show red error states on all inputs |
| Forgot Password | `screenshots/forgot-password.png` | Email field with Send Reset Link button |
| Forgot Password (success) | `screenshots/forgot-password-success.png` | Green success state after submitting a valid email |
| Reset Password | `screenshots/reset-password.png` | Two password fields with requirements checklist visible |
| Reset Password (success) | `screenshots/reset-password-success.png` | Green "Password updated!" confirmation state |
| Dashboard (desktop) | `screenshots/dashboard-desktop.png` | Full dashboard at 1280px — navbar, banner, 4 stat cards, actions + activity side by side |
| Dashboard (tablet) | `screenshots/dashboard-tablet.png` | Same page at 768px — stat cards 2×2, activity stacked below actions |
| Dashboard (mobile) | `screenshots/dashboard-mobile.png` | Same page at 375px — hamburger menu, single-column layout |

### How to take screenshots
- **Chrome / Edge**: Open DevTools → Toggle device toolbar (`Ctrl+Shift+M`) → Select device or set custom width → Right-click page → "Capture screenshot"
- **Firefox**: Open DevTools → Responsive Design Mode (`Ctrl+Shift+M`) → Camera icon in toolbar

---

## Project Structure

```
CampusPe/
├── login.html            # Sign in page
├── register.html         # New account registration
├── forgot-password.html  # Password recovery request
├── reset-password.html   # Set new password
├── dashboard.html        # Post-login student dashboard
├── style.css             # Global design system
├── screenshots/          # Page screenshots (add before submitting)
└── README.md             # This file
```

---

## Pages & Features

### 1. `login.html` — Sign In
- Email + password input fields with icon groups
- "Forgot password?" inline link
- "Remember me" checkbox
- Sign In button → redirects to `dashboard.html`
- Link to `register.html`

### 2. `register.html` — Create Account
- Full Name, Email, Password, Confirm Password fields
- Live validation on every field (green ✓ / red ✗ border + feedback text)
- Password strength meter (Weak → Fair → Good → Strong)
- Password visibility toggle on both password fields
- Terms & Privacy Policy checkbox (required)
- Submit guard — prevents navigation if any field is invalid
- Link back to `login.html`

### 3. `forgot-password.html` — Forgot Password
- Single email field with live format validation
- Two states in one page:
  - **Form state** — email input + Send Reset Link button
  - **Success state** — green confirmation badge, displays submitted email, "Resend email" link (3-second cooldown)
- Back to Sign In link

### 4. `reset-password.html` — Reset Password
- New Password + Confirm Password fields
- Password visibility toggle on both fields
- Live password strength bar + 4-item requirements checklist
- Two states in one page:
  - **Form state** — password inputs + Update Password button
  - **Success state** — green "Password updated!" confirmation + Go to Sign In button
- Back to Sign In link

### 5. `dashboard.html` — Student Dashboard
- Sticky responsive navbar with hamburger menu on mobile
- Welcome banner with active session indicator
- 4 stat cards: Enrolled Courses, Achievements, Balance, Avg. Progress
- Quick Actions grid: Enroll Course, Add Funds, Schedule, Support
- Recent Activity feed with 5 timeline items
- Profile card with avatar, verified badge, and mini stats
- Course Progress section with 5 color-coded progress bars

---

## Navigation Flow

```
Login ──────────────────────────────► Dashboard
  │                                       │
  ├──► Register ──────────────────► Login │
  │                                       │
  └──► Forgot Password                Logout
            │
            ▼
       Reset Password ──────────────► Login
```

---

## Tech Stack

| Technology | Version | Purpose |
|---|---|---|
| HTML5 | — | Page structure and semantics |
| Bootstrap | 5.3.3 | Grid system, utilities, components |
| Bootstrap Icons | 1.11.3 | Icon library |
| Google Fonts | — | Inter (body) + Poppins (headings) |
| Vanilla JS | ES6+ | Form validation, UI interactions |
| CSS Custom Properties | — | Design tokens and theming |

> No build tools, no frameworks, no dependencies to install. Everything runs directly in the browser.

---

## Design System (`style.css`)

The shared stylesheet defines:

- **CSS variables** — brand colors, gradients, shadows, radii, transitions
- **Typography** — Inter for body text, Poppins for headings and values
- **Component classes** — `cp-card`, `cp-btn-primary`, `cp-navbar`, `cp-stat-card`, etc.
- **Responsive breakpoints** — xs / sm / md / lg / xl with fluid font and spacing scaling
- **Animations** — `cp-fade-up` page entrance, `cp-pop` success badge, staggered stat card delays

---

## Responsive Breakpoints

| Breakpoint | Width | Layout |
|---|---|---|
| Mobile (xs) | < 576px | Single column, compact padding, hamburger nav |
| Mobile landscape (sm) | 576–767px | Auth card narrows, reduced icon sizes |
| Tablet (md) | 768–991px | Dashboard 2×2 stat grid, stacked sections |
| Laptop (lg) | 992–1199px | Side-by-side actions + activity, 4-col stats |
| Desktop (xl) | ≥ 1200px | Full layout, larger values, 2-col progress grid |

---

## Getting Started

1. Clone or download the repository
2. Open `login.html` in any modern browser
3. No installation or build step required

```bash
git clone https://github.com/YOURUSERNAME/campuspe-auth-ui.git
cd campuspe-auth-ui
# Open login.html in your browser
```

---

## GitHub Upload Checklist

- [ ] All 5 HTML files present and opening correctly in browser
- [ ] `style.css` loads without 404 (check browser DevTools → Network tab)
- [ ] Google Fonts load (requires internet connection)
- [ ] Bootstrap CSS + JS load from CDN (requires internet connection)
- [ ] All page-to-page links work correctly
- [ ] Screenshots folder added with at least one image per page
- [ ] Repository set to **Public**
- [ ] `README.md` updated with your actual GitHub username in the clone URL

---

## Notes

- This is a **front-end only** proof of concept — no backend, database, or real authentication logic
- Form submissions use `method="get"` for demo navigation only
- Passwords are never stored or transmitted
- For production use, replace form actions with a proper backend API and add HTTPS

---

*Built with Bootstrap 5 · Designed for CampusPe*
