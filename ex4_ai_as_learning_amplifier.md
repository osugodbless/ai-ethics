## Phase 1: Build Foundation (you first)
### Simple scenario

**Disaster Recovery**

A flood wrecked havoc in a small village and all networks are down.

People who are rescuing and treating wounded individuals need to communicate with each other. So I'll deploy a wireless ad hoc network (MANET)

### Devices in the Network

- D1    command center telephone
- D2    Ambulance tablet
- D3    Rescue team 1 radio
- D4    Rescue team 2 radio
- D5    Field coordinator phone
- D6    Medical tent phone

All devices have Wi-Fi radio, battery power and ability to route packets.

### Design Decision: I'll use a Reactive Routing Protocol (Ad hoc on-demand distance vector)

**Why AODV Is the Best Choice Here**
1. Mobility

- Rescue teams move constantly.

- AODV:

    - Creates routes only when needed

    - Better for mobility

2. Battery-Powered Devices

These devices run on batteries and reactive protocols saves battery power.

3. Limited Bandwidth

Disaster areas have:

- Interference

- Limited spectrum

- No infrastructure

AODV reduces:

- Unnecessary control traffic


## Phase 2: Strategic AI Use
Edge case 1: What happens if the command center suddenly sends continous updates to all teams?
Edge case 2: What happens if any device move far away?

## Phase 3: Real Application
1. Smart Home IoT Network (Static/Low Mobility) 
Protocol: RPL or AODV.
Scenario: 10 devices (Smart lights, thermostat, sensors, security camera) in a home.
Topology: A central home gateway acts as the root node (sink). Other devices are scattered around, some connecting directly to the gateway, others through intermediate devices (multi-hop) to reach the internet.
Operation: Sensors send data periodically (temperature), while devices like cameras may send higher bursts of data. RPL organizes this into a destination-oriented directed acyclic graph (DODAG). 
2. Ad-Hoc Meeting Room Setup (High Mobility)
Protocol: AODV or DSR.
Scenario: 7–8 laptops/smartphones sharing files directly without a Wi-Fi access point.
Topology: Nodes are in close proximity (e.g., 20m x 20m area). Devices move around the room, changing links frequently.
Operation: Node A wants to send a file to Node D. AODV initiates a Route Request (RREQ). If a link breaks, the route is repaired, and a Route Error (RERR) is sent. 
3. Industrial Sensor Monitoring (Low Mobility, Critical Reliability)
Protocol: OLSR or AODV.
Scenario: 6 nodes monitoring machinery on a factory floor.
Topology: A straight line or cluster formation. Nodes are placed 10–50m apart.
Operation: Nodes must transmit data to a control center. Since the environment might have high interference, a protocol like OLSR ensures that routes are always available, minimizing lookup delays, while AODV ensures energy efficiency if nodes are battery-powered.

## Reflection:

### % human judgment vs. AI contribution
55% vs 45%

### Could you defend decisions without AI?
Yes

### What will you still remember in 6 months?
What routing is all about and how it helps devices communicate across a network.

### Did AI make you sharper, or think for you?
Made me sharper.