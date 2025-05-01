# Pick & Place App for Franka Emika R3 (Franka Desk / RIDE)

This project contains a custom Pick & Place Desk App developed for the Franka Emika R3 robot using the **RIDE CLI** toolchain and the **Franka Desk** environment.

It includes:
- A user-friendly GUI interface for teaching poses and gripper widths
- A full pick-and-place motion state machine
- A stylized custom icon and SVG-based visuals
- Velocity slider for dynamic tuning
- Pre-integrated teaching steps for Desk

---

## Repository Structure

```
franka_ride_pick_place/
├── bundles/
│   └── pick_place/
│       ├── manifest.json
│       ├── sources/
│       │   └── pick_place.lf
│       └── resources/
│           ├── icon.svg
│           ├── object.svg
│           ├── gripper_holding.svg
│           ├── gripper_opened.svg
```

---

## Requirements

- Ubuntu 22.04 with internet access
- Franka Emika R3 robot (in lab)
- Franka Desk + RIDE App Development feature
- `ride-cli` version `>= 1.1.1` installed from Franka World Hub

---

## Setup Instructions (Before Going to Lab)

1. Clone the repository:
   ```bash
   git clone https://github.com/DimiSf/franka_ride_pick_place.git
   cd franka_ride_pick_place
   ```

2. Check that the structure is correct and files are present under:
   ```
   bundles/pick_place/sources/pick_place.lf
   bundles/pick_place/resources/icon.svg
   ```

3. Prepare your `.lf` logic and verify formatting. Do not compile remotely yet.

---

## Setup in Lab (Once at Robot)

1. Install `ride-cli` (only on lab PC):
   ```bash
   sudo apt install ./ride-cli_1.1.1-1_jammy_amd64.deb
   ```

2. Compile your bundle:
   ```bash
   ride bundle compile bundles/pick_place
   ```

3. Log in to the robot:
   ```bash
   ride login <robot_ip>
   ```

4. Upload the compiled bundle:
   ```bash
   ride bundle install pick_place.bundle
   ```

---

## How the App Works (User Flow)

This app expects you to teach the following in Franka Desk:

- `pick_pose`: Cartesian pick location
- `place_pose`: Cartesian place location
- `gripper_open_width`: Width before grasp
- `gripper_closed_width`: Width after grasp
- `velocity`: Slider-controlled speed

During execution:
- Robot moves to `pick_pose`
- Closes gripper
- Moves to `place_pose`
- Opens gripper
- Motion completes

---

## Notes

- The app uses a custom icon defined in `resources/icon.svg`
- All parameters are accessible from the GUI for teaching
- No robot simulation or execution can be done without Franka Desk and a real robot

---


## License

This project is for academic and internal research use. Contact me for licensing questions.
