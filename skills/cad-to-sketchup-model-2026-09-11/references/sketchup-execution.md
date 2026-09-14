# SketchUp Execution Reference

## Authorization gates

- Do not inspect, open, control, close, restart, or retry SketchUp before the user explicitly confirms modeling should begin.
- Prefer a SketchUp window opened by the user.
- Automatic startup requires separate explicit authorization.
- Normal user updates must hide bridge, PID, loader, registry, Ruby, port, and status-file details.

## Choose the execution path

- SketchUp already open and target confirmed: use `send_su_code.ps1 -UserConfirmedBuild`.
- SketchUp closed: ask the user to open the intended target and wait.
- User separately authorizes automatic startup: use `run_su_task.ps1 -UserConfirmedBuild -UserAuthorizedAutoStart`.
- Need to verify available targets: use `inspect_bridge_targets.ps1`.
- Bridge not installed: use `install_su_bridge.ps1`, then restart SketchUp once.

## Install

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\install_su_bridge.ps1
```

Specify another installed version when needed:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\install_su_bridge.ps1 -SketchUpVersion "SketchUp 2025"
```

## Diagnose

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\inspect_bridge_targets.ps1
```

Registry entries older than 15 seconds may be stale. If a target cannot be reached, restart SketchUp or use **Extensions > Codex Bridge > Restart Bridge**.
Keep these diagnosis details out of normal user-facing progress updates.

## Targeting

- One reachable target: allow automatic selection.
- Multiple targets: present model titles and paths to the user; then use `-TargetPid` or `-ModelPath`.
- Unsaved models have no path; target them by PID.

## Task script contract

- Start and commit a SketchUp operation; abort it on failure.
- Remove or update only the script's own named root group.
- Write a status/report file for detailed output.
- Prefer `save_copy` or a new output path.
- Verify generated geometry after execution.
- For production, require the `build` workflow gate, run only the current
  `build_sketchup_production_model.rb`, then bind its result with
  `finalize_sketchup_build.py`.
- Reject an active path different from the confirmed white model and reject
  unsaved source-model changes. Save production to a new output SKP.
