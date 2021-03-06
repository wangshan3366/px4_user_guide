# LAND Flight Mode

The LAND flight mode causes the vehicle to land at the position where the mode was engaged.

The specific behaviour for each vehicle type is described below.

> **Note** 
> This mode is automatic (RC control is disabled [by default](../advanced_config/parameter_reference.md#COM_RC_OVERRIDE) except to change modes).

## Multi-Copter (MC)

The vehicle will land at the location at which the mode was engaged. The vehicle descends at the rate specified in `MPC_LAND_SPEED` until it hits the ground.

Landing is affected by the following parameters:

Parameter | Description
--- | ---
[MPC_LAND_SPEED](../advanced_config/parameter_reference.md#MPC_LAND_SPEED) | The rate of descent during landing. This should be kept fairly low as the ground conditions are not known.

## Fixed Wing (FW)

The vehicle will turn and lands at the location at which the mode was engaged. Fixed wing landing logic and parameters are explained in the topic: [Landing (Fixed Wing)](../flying/fixed_wing_landing.md).

> **Note** Often a FW vehicle will follow a fixed landing trajectory to ground (it will not attempt a flared landing). This is because in LAND mode the vehicle may not know ground altitude and will assume it is at sea level. As ground level may be much higher a vehicle will often reach the ground at an altitude above where flare logic would be engaged.


## VTOL

A VTOL follows the LAND behavior and parameters of [Fixed Wing](#fixed-wing-fw) when in FW mode, and of [Multicopter](#multi-copter-mc) when in MC mode. When  [NAV_FORCE_VT](../advanced_config/parameter_reference.md#NAV_FORCE_VT) is set (default: on) a VTOL in FW mode will transition back to MC just before landing.