## Why I built this: As an omakase server, I often have to check reservations ahead of time to make sure the counter isn’t booked with gaps in between. A small mistake in seat assignment can block an otherwise valid booking (especially when there are multiple seatings in a day). This project simulates a simple fix that could be done: an always-compact seating policy that automatically reassigns parties to keep seats contiguous.

# Seatings-Reservation-Idea
Omakase booking demo with customer + internal views; auto-compacts seats after every booking or cancellation.
# Omakase Always-Compact Seating (Anti-Scattering Reservations)

A small notebook project modeling an omakase counter (default: **16 seats**) where:
- parties must sit together (contiguous seats),
- customers do **not** choose seat numbers,
- hosts can rearrange seat assignments behind the scenes.

## Why this matters (Omakase problem)
Reservation platforms can store seat assignments in a scattered way, causing **false sold-out** cases.

Example on a 16-seat counter:
- bookings: 1–2, 3–4, 9–14  
- free seats: 5–8 (4 seats) and 15–16 (2 seats) → total free = 6  
A party of 5 cannot book because no contiguous block of 5 exists, even though capacity is there.

## Solution: Always-Compact Policy
After every booking or cancellation, the system **reassigns all reservations** so seating is packed contiguously starting from seat 1.  
This eliminates fragmentation and prevents false sold-out outcomes.

## What’s in this repo
- `omakase_app.ipynb' containing the full code

### Requirements
- Python 3.9+
- `ipywidgets`
- `pandas`

Install:
```bash
pip install ipywidgets pandas
