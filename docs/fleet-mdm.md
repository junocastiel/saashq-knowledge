# Fleet MDM

Date: 2026-06-24  
Status: Draft  
System: Fleet MDM, Android Enterprise, Google enterprise binding, GitHub Pages, Cloudflare DNS  
Sensitive data: Masked

## Goal

Use [Fleet](https://fleetdm.com/guides/android-mdm-setup) as the MDM layer for Android Enterprise so a managed Android phone can be configured and recovered with minimum dependence on the phone user.

The main target device is a family member's Android phone, so the design should favor remote manageability, simple enrollment, and clear recovery notes.

## Planned Final Configuration

- MDM server: Fleet.
- Public documentation: this MkDocs site at `https://blog.saashq.in/`.
- Admin email domain: `mdm.saashq.in`.
- Email handling: Cloudflare Email Routing forwards MDM mail to a masked Gmail destination.
- Android management mode: Android Enterprise, preferably fully managed device owner mode after factory reset.
- DNS provider: Cloudflare.

## Why Fleet

Fleet is preferred here because the goal is to avoid writing a custom Android control system from scratch.

The expected MDM needs are:

- Enroll and track Android devices.
- Manage Android Enterprise settings.
- Keep setup repeatable from documentation.
- Use a self-hostable or controllable server-side system.

## Important Android Enterprise Notes

- A normal personal Gmail account on the phone is not the same thing as the Android Enterprise admin binding.
- For strongest control, the phone should be enrolled during fresh setup after factory reset.
- Device owner mode is the important mode for full-device management.
- A phone that is already set up normally cannot usually be converted into full device owner mode just by installing an app.
- Factory reset protection and theft recovery behavior depend on Android Enterprise support, device vendor behavior, Google services, and the selected MDM feature set.

## Setup Flow

1. Prepare the Fleet server and confirm it is reachable from the internet.
2. Prepare a stable admin email under `mdm.saashq.in`.
3. Configure Android Enterprise binding in Fleet.
4. Factory reset the Android phone.
5. Start Android setup from the welcome screen.
6. Enroll the device into Fleet using the Fleet-supported Android Enterprise enrollment method.
7. Confirm the device appears in Fleet.
8. Apply required restrictions and location-related policies.
9. Test the actual recovery workflow before handing the phone back to the user.

## Cloudflare Email Dependency

Fleet-related emails can use addresses under `mdm.saashq.in`.

The email routing setup is documented separately:

[Cloudflare Email Routing](cloudflare-email-routing.md)

## Device Policy Checklist

Use this as the first policy checklist. Adjust after testing on the Xiaomi device.

- Prevent the user from disabling required management components.
- Keep Wi-Fi/mobile data behavior as manageable as Android allows.
- Keep location services enabled where policy support exists.
- Enable remote lock and wipe if supported.
- Confirm whether Enterprise Factory Reset Protection is available in the chosen Fleet setup.
- Record exact behavior after SIM removal, new SIM insertion, and factory reset.

## Verification Checklist

Before considering the setup usable:

- Device enrolls successfully after factory reset.
- Device appears online in Fleet.
- Fleet can send a remote command to the device.
- Location or inventory data updates as expected.
- Removing the SIM does not break management once internet is restored.
- Inserting another SIM and bringing the phone online produces the expected managed behavior.
- Factory reset behavior is understood and documented.

## Open Questions

- Exact Fleet hosting target: VPS, home server, or other hosting.
- Exact Android Enterprise binding account to use.
- Exact Xiaomi model and Android/HyperOS version.
- Whether the final setup supports Enterprise Factory Reset Protection.
- Which restrictions Fleet exposes for this specific Android device.
