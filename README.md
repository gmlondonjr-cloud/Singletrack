# SINGLETRACK

A browser-playable first-person mountain biking prototype for iPhone, iPad and desktop. Includes faceted scenery, endless trail generation, five repeating terrain regions, pedal/brake controls, calibrated orientation input, bunny hops, manuals, airborne whips, crashes, distance records and three distance-based bike upgrades.

## Run

From this directory run `python3 -m http.server 8080 --directory dist`, then open http://localhost:8080. For iPhone/iPad tilt controls, host `dist` over HTTPS and open it in Safari. Tap Drop In, then Enable Tilt, grant sensor permission and hold the device in your normal playing position. Calibrate again after changing orientation. If sensors are unavailable, drag the scenery to steer and swipe up to hop.

Desktop controls: W pedal, S brake, A/D or left/right arrows steer, up arrow manual, Space bunny hop, Q/E whip, P pause. Release a whip and straighten the bike before landing.

## Current scope

This is a browser prototype, not a native iOS project or an App Store release. Rendering uses projected canvas polygons. Physics use a fixed 120 Hz timestep, gravity, slope acceleration, drag, lateral slip, airborne velocity and landing alignment. They are an approximation, not a validated two-wheel rigid-body simulation. Terrain generation combines deterministic curves and obstacle placement with repeating jump/drop templates; a production generator would need richer feature selection and rideability constraints. Progress is stored in this browser only. Sound is a simple synthesized riding tone.

Automated checks cover acceleration, braking, hopping, landing, off-trail crashes, pause/resume, upgrades and rendering all five terrain palettes. Run `node check.cjs`. Browser visuals, sensor axis mapping, tilt gestures and riding feel require testing on physical iOS devices. No browser QA was available in the build environment. Hosted publication was blocked by the absent Sites source workflow helper.

For a production iOS version, use this as the interaction sketch for a native engine implementation with Core Motion input, tire contact and suspension physics, and repeated device playtesting.
