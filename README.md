# franka_ride_pick_place

 What Are RIDE Bundles?

A bundle is a reusable package of logic (like a mini-library) that contains prebuilt state machines for things like:

    Robot motion

    Gripper control

    Parallel execution

    Pose teaching

    Logic blocks (like conditions or waits)

You declare which bundles you use in your manifest.json.

The manifest.json file indicates the name and the version of a bundle. When installing a bundle on a robot which already has a bundle with the same name, it will only be updated if the version is the same or newer.
