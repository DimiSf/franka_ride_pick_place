Test: Verify RIDE CLI Setup with test_hello Bundle

Before installing and running the full pick_place app, you can test your RIDE CLI setup using the simple test_hello bundle.

This app:

    Does not move the robot

    Simply prints: "Hello from RIDE CLI!"

    Helps verify:

        Robot is reachable (ride login)

        Bundle compilation and installation works

        Logging output is functional

Run This Test in the Lab

From your repo root:

# 1. Log in to the robot
ride login "<robot-ip>"

# 2. Compile the test bundle
ride bundle compile bundles/test_hello

# 3. Install the bundle
ride bundle install bundles/test_hello.bundle

# 4. Stop any currently running RIDE app
ride cli stop

# 5. In one terminal, start logging output
ride cli log

# 6. In another terminal, start the test bundle
ride cli start -t HelloWorld

If successful, your log window will show:

Hello from RIDE CLI!

This confirms your RIDE CLI and connection setup is correct.
