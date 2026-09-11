# Leaves 1.21.8 keepalive handoff fix

This repository is based on `LeavesMC/Leaves` tag `1.21.8-138-9331167`, the
same build currently reported by the LunWorld Server 1 and Server 2 logs.

## Incident evidence

Velocity recorded repeated `kicked ... disconnect.timeout` events during
backend switches. Leaves recorded `Disconnecting ... for sending keepalive
response ... out-of-order`. This is the listener-handoff keepalive race fixed
upstream by Paper PR #13712.

## Current status

The upstream fix has been prepared as `leaves-server/paper-patches/features/
0017-Keepalive-listener-handoff.patch`. It must pass `./gradlew applyAllPatches`
and `./gradlew createMojmapLeavesclipJar` before any server deployment.

Do not replace the live server JAR from this repository until those checks pass.
