# Lab Setup & Safety Checklist

> Run before each session. Most module failures come from skipping items 2, 4, or 7 in the per-session list.

---

## One-time setup (per semester)

### Hardware
- [ ] One Reachy Mini WiFi per 3–4 students
- [ ] Travel router (e.g., GL.iNet) configured as isolated lab WiFi
- [ ] Router has a manual switch for upstream internet (off by default)
- [ ] Each robot labeled with hostname (`reachy-lab-XX`) and colored tape
- [ ] One student laptop per student, admin rights confirmed
- [ ] One TA console laptop, separate

### Software baseline (each laptop)
- [ ] Reachy Mini SDK installed in dedicated virtualenv; **SDK version pinned** in module README
- [ ] `mitmproxy`
- [ ] `bettercap`
- [ ] Wireshark / `tshark` with mDNS + WebSocket profile saved
- [ ] Course Git repo cloned
- [ ] Per-student fork created

### Network
- [ ] Lab SSID broadcasts only inside the room (verified with phone outside the door)
- [ ] WPA2-PSK with rotating per-semester password (stored in password manager, not whiteboard)
- [ ] Confirmed no bridge to campus network
- [ ] Internet switch tested (on / off / on)

### Reset
- [ ] Documented script that wipes robot state to known-good image in <5 min
- [ ] Reset script tested with stopwatch

---

## Per-session pre-class checklist

- [ ] Lab WiFi up, no upstream (verified with phone)
- [ ] All robots powered on and reachable from TA console
- [ ] Camera shutters closed (or covered) until needed
- [ ] Audit log destination on TA laptop has free space
- [ ] Responsible-disclosure reminder printed and visible in room
- [ ] "Stop word" announced at start of session (any student can say it; honor without follow-up)
- [ ] Module-specific items (see module README)

---

## Per-session post-class checklist

- [ ] Revoke any tokens issued during class
- [ ] Restore camera shutters
- [ ] Move packet captures off student laptops to course storage
- [ ] Delete captures from student devices
- [ ] Power down robots
- [ ] Lab door locked
- [ ] One-paragraph incident note written for anything that surprised you

---

## End-of-semester checklist

- [ ] Tag the course repo with semester label
- [ ] Write one-page "what broke this time" note for next instructor
- [ ] Rotate lab WiFi password
- [ ] Inventory hardware (robots, routers, cables)
- [ ] Decommission temporary accounts (sandbox PyPI account, LLM API keys)
- [ ] File data-retention compliance note per IRB protocol
