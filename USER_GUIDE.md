# CheckInn User Guide & Operational Manual 📖

This guide details how to operate the **CheckInn** platform across all user roles.

---

## 1. Platform Personas & URL Hierarchy

CheckInn divides responsibilities across four distinct personas:

| Persona | Audience | Portal URL | Primary Responsibility |
|---|---|---|---|
| **Super Admin** | Platform Owner | `/super-admin` | Manage society licenses, create societies, view system logs. |
| **Society Admin** | Managing Committee | `/admin` | Society settings, configure checkpoints & checklists, assign Estate Managers. |
| **Facility Manager** | Estate / Ops Manager | `/manager` | Daily operations, print QR signs, onboard workers & issue PINs. |
| **Service Provider** | Field Workers / Techs | `/worker` & `/checkin` | Enter PIN, scan station QR code, submit inspection checklists. |

---

## 2. Managing Committee (Society Admin) Guide

### Accessing the Portal
1. Navigate to `/admin/login`.
2. Sign in with your registered Google account or managing committee credentials.

### Creating Checkpoints
1. Go to **Checkpoints** in the navigation bar.
2. Click **Add New Checkpoint**.
3. Enter the Station Name (e.g. *"STP Aeration Tank A"*, *"Main Pump Room"*, *"DG Set Bay 2"*).
4. *(Optional)* Add Dynamic Checklist items:
   * Field Label (e.g. *Water Level (m)*)
   * Field Type (`number`, `boolean`, `text`, `select`)
   * Range / Validation bounds (e.g. Min 1, Max 10).
5. Save the checkpoint.

### Downloading QR Signage
1. Click **View QR** on any checkpoint card.
2. Click **Download High-DPI PNG** or **Download SVG**.
3. Print and laminate the QR code, then mount it physically at the facility station.

---

## 3. Estate / Facility Manager Guide

### Onboarding a Service Provider
1. Log in at `/manager/login`.
2. Navigate to **Workers**.
3. Click **Onboard Service Provider**.
4. Enter the worker's Full Name, Phone Number, and Trade / Role (e.g. *STP Technician*, *Electrician*, *Security*).
5. The system will automatically generate a secure numeric PIN for the worker.
6. Hand over the PIN to the worker.

### Enabling or Disabling Worker Self-Registration
1. Go to **Settings** (`/manager/settings`).
2. Toggle **Allow Worker Self-Registration**.
   * When enabled, new technicians can self-register at `/worker/register` by providing their phone number and choosing their own PIN.
   * When disabled, self-registration is rejected with HTTP 403.

---

## 4. Service Provider (Worker) Guide

### Logging In & Starting a Shift
1. On your smartphone browser, open `/worker/login`.
2. Enter your Phone Number, Select your Society, and enter your numeric PIN.
3. If you work at multiple societies, you can switch between them at any time from the society selection drawer.

### Scanning a Facility Checkpoint
1. Tap the big green **"Scan Station QR"** button.
2. Allow camera access.
3. Align the camera with the physical QR code mounted at the facility station.
4. If the station has an inspection checklist, fill in the prompt values (e.g. meter readings or checkboxes).
5. Tap **Submit Check-in**.
6. A green confirmation banner will appear with the station name, server-verified timestamp, and check-in ID.
