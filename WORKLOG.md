# Worklog

## 2026-10-20 - Newt device bring-up and guest hosting (not yet verified on screen)

**What changed**: No code commits this session. The working tree still holds the earlier bundle-identifier rename across 18 files; it was not reviewed or committed here. A device build for Newt now succeeds with team `84M4ZF255G`, the team Xcode accepts under the oliver@ames.consulting account. `PV3W52NDZ3` returns "No Account for Team." The build was run once with the `increased-memory-limit` entitlement removed from `LiveProcess/LiveProcess.entitlements`; that edit was reverted and the file is back to its pre-test contents. LiveContainer was installed and launched on Newt as `com.oliverames.stagemanager.84M4ZF255G`. A prototype device build was copied into LiveContainer's `Documents/Applications` on Newt.

**Decisions made**: Device builds use team `84M4ZF255G`. The memory-limit entitlement stays in the repo; removing it for test builds is not a committed change.

**Resolved this session**: The signing team for Newt is identified and device builds succeed. Xcode's account pane accepts `84M4ZF255G`.

**Still open**:
- `increased-memory-limit` on the `LiveProcess` target fails provisioning for this team. Large guest apps may hit memory limits until it is granted or removed.
- Guest hosting is unverified on device. LiveContainer runs (PID 8112), but no guest process has started, and the screen has not been viewed. Xcode's device-interaction tools do not list Newt, and the USB screenshot service rejects requests.
- Keyboard input is unverified. Injected text did not reach the prototype's Notes window on the Duo simulator.
- The external display scene is unverified on hardware.

**Left off at**: LiveContainer is running on Newt with no guest process. Next step needs one of: select Newt in Xcode's Devices window, approve iPhone Mirroring, or tap the guest on Newt.

**Open questions**:
- Commit the bundle-identifier rename as one change, or split it?
- Issues are disabled on this repository. Where should these open items be tracked?

---
