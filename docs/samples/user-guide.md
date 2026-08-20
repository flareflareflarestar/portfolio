# User Guide: Setting Up a New Flight Route

## Overview

Using Altus, flight planners can quickly set up new flight routes that can be scheduled, and assigned to aircraft and pilots.

---

## Prerequisites

!!! warning "Routes Management Approval Required"
    You **must** receive prior approval from a team member from Routes Management before setting up a new flight route. Creating unapproved routes may result in compliance violations and disciplinary action.

- Active **Flight Planner** role in Altus.
- Required flight details on hand: departure and arrival airport codes (ICAO/IATA), flight category (commercial, freight, etc.), and planned waypoints.

---

## Step-by-Step Instructions

### Step 1: Create a New Route

1. Log in to **Altus** via the ID card reader to verify your identity.
2. Navigate to **Flight Management** > **Create New Route**.
3. In the **Route Name** field, enter a descriptive title (for example `2026 Summer YYZ-MEX Additional`).
4. Click **Next**.
5. Select the appropriate flight category in the **Flight Category** dropdown menu.
6. Choose either **One-way** or **Return** as the route type.
7. Enter the origin and destination using valid ICAO or IATA codes in the **Departure Airport** and **Arrival Airport** fields.
8. In the **Waypoints** field, enter the planned waypoints in sequential order from origin to destination, separated by commas (CSV format).
9. Click **Next**.

!!! info "Flight Numbers"
    Flight numbers generate automatically using the next available sequence number. You can manually change the flight number during the review step.

### Step 2: Review and Activate

1. Review the flight details and update any incorrect information.

    !!! info "Complementary Return Routes"
        If the route is set to **Return**, Altus will automatically generate a paired return route with reversed airports and waypoints.

2. Click **Confirm New Route**.
3. Navigate to **Flight Management** > **View Routes** > **Inactive**.

    !!! info "Default Status"
        New routes are set to "*Inactive** by default to prevent unauthorised or premature flight scheduling.

4. Locate your newly created route and click **Activate Route**.

---

## Troubleshooting

| Issue | Possible Causes | Solutions |
|:---|:---|:---|
| 100 Airport Not Found | Invalid ICAO/IATA code | Enter a valid ICAO/IATA code |
| 143 Unexpected Waypoint Data | Waypoint formatting error | Format waypoints with CSV |
| Route not appearing in scheduling menus | Route status is **Inactive** | Activate route |
