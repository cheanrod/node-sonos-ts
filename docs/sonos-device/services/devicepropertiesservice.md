---
layout: default
title: DevicePropertiesService
parent: Services
grand_parent: Sonos device
---
# DevicePropertiesService
{: .no_toc }

Modify device properties, like led status and stereo pairs -

```js
const SonosDevice = require('@svrooij/sonos').SonosDevice
const sonos = new SonosDevice('192.168.x.x')
sonos.DevicePropertiesService.OneOfTheMethodsBelow({...})
```

All methods that require input expect an object with the specified parameters, even if it only requires one parameter.

1. TOC
{:toc}

---

### AddBondedZones

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **ChannelMapSet** | `string` |  |

### AddHTSatellite

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **HTSatChanMapSet** | `string` |  |

### CreateStereoPair

Create a stereo pair (left, right speakers), right one becomes hidden - only supported by some players

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **ChannelMapSet** | `string` | example: RINCON_B8E9375831C001400:LF,LF;RINCON_000E58FE3AEA01400:RF,RF |

### EnterConfigMode

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **Mode** | `string` |  |
| **Options** | `string` |  |

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **State** | `string` |  |

### ExitConfigMode

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **Options** | `string` |  |

### GetAutoplayLinkedZones

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **Source** | `string` |  |

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **IncludeLinkedZones** | `boolean` |  |

### GetAutoplayRoomUUID

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **Source** | `string` |  |

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **RoomUUID** | `string` |  |

### GetAutoplayVolume

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **Source** | `string` |  |

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentVolume** | `number` |  |

### GetButtonLockState

No input parameters

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentButtonLockState** | `string` |  |

### GetButtonState

No input parameters

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **State** | `string` |  |

### GetHouseholdID

No input parameters

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentHouseholdID** | `string` |  |

### GetLEDState

No input parameters

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentLEDState** | `string` |  |

### GetUseAutoplayVolume

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **Source** | `string` |  |

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **UseVolume** | `boolean` |  |

### GetZoneAttributes

No input parameters

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentZoneName** | `string` |  |
| **CurrentIcon** | `string` |  |
| **CurrentConfiguration** | `string` |  |

### GetZoneInfo

No input parameters

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **SerialNumber** | `string` |  |
| **SoftwareVersion** | `string` |  |
| **DisplaySoftwareVersion** | `string` |  |
| **HardwareVersion** | `string` |  |
| **IPAddress** | `string` |  |
| **MACAddress** | `string` |  |
| **CopyrightInfo** | `string` |  |
| **ExtraInfo** | `string` |  |
| **HTAudioIn** | `number` |  |
| **Flags** | `number` |  |

### RemoveBondedZones

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **ChannelMapSet** | `string` |  |
| **KeepGrouped** | `boolean` |  |

### RemoveHTSatellite

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **SatRoomUUID** | `string` |  |

### SeparateStereoPair

Separate a stereo pair - only supported by some players

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **ChannelMapSet** | `string` | example: RINCON_B8E9375831C001400:LF,LF;RINCON_000E58FE3AEA01400:RF,RF |

### SetAutoplayLinkedZones

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **IncludeLinkedZones** | `boolean` |  |
| **Source** | `string` |  |

### SetAutoplayRoomUUID

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **RoomUUID** | `string` |  |
| **Source** | `string` |  |

### SetAutoplayVolume

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **Volume** | `number` |  |
| **Source** | `string` |  |

### SetButtonLockState

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **DesiredButtonLockState** | `string` |  |

### SetLEDState

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **DesiredLEDState** | `string` |  |

### SetUseAutoplayVolume

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **UseVolume** | `boolean` |  |
| **Source** | `string` |  |

### SetZoneAttributes

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **DesiredZoneName** | `string` |  |
| **DesiredIcon** | `string` |  |
| **DesiredConfiguration** | `string` |  |

## DevicePropertiesService event

```js
const SonosDevice = require('@svrooij/sonos').SonosDevice
const sonos = new SonosDevice('192.168.x.x')
sonos.DevicePropertiesService.Events('serviceEvent', (data) => {
  console.log(data);
});
```

The **DevicePropertiesService** emits events with these properties. Not all properties are emitted everytime.

| parameter | type |
|:----------|:-----|
| **AirPlayEnabled** | `boolean` |
| **AutoplayIncludeLinkedZones** | `boolean` |
| **AutoplayRoomUUID** | `string` |
| **AutoplaySource** | `string` |
| **AutoplayUseVolume** | `boolean` |
| **AutoplayVolume** | `number` |
| **AvailableRoomCalibration** | `string` |
| **BehindWifiExtender** | `number` |
| **ButtonLockState** | `string` |
| **ChannelFreq** | `number` |
| **ChannelMapSet** | `string` |
| **ConfigMode** | `string` |
| **Configuration** | `string` |
| **CopyrightInfo** | `string` |
| **DisplaySoftwareVersion** | `string` |
| **ExtraInfo** | `string` |
| **Flags** | `number` |
| **HTAudioIn** | `number` |
| **HTBondedZoneCommitState** | `number` |
| **HTFreq** | `number` |
| **HTSatChanMapSet** | `string` |
| **HardwareVersion** | `string` |
| **HasConfiguredSSID** | `boolean` |
| **HdmiCecAvailable** | `boolean` |
| **HouseholdID** | `string` |
| **IPAddress** | `string` |
| **Icon** | `string` |
| **Invisible** | `boolean` |
| **IsIdle** | `boolean` |
| **IsZoneBridge** | `boolean` |
| **KeepGrouped** | `boolean` |
| **LEDState** | `string` |
| **LastChangedPlayState** | `string` |
| **MACAddress** | `string` |
| **MicEnabled** | `number` |
| **MoreInfo** | `string` |
| **Orientation** | `number` |
| **RoomCalibrationState** | `number` |
| **SatRoomUUID** | `string` |
| **SecureRegState** | `number` |
| **SerialNumber** | `string` |
| **SettingsReplicationState** | `string` |
| **SoftwareVersion** | `string` |
| **SupportsAudioClip** | `boolean` |
| **SupportsAudioIn** | `boolean` |
| **TVConfigurationError** | `boolean` |
| **VoiceConfigState** | `number` |
| **WifiEnabled** | `boolean` |
| **WirelessLeafOnly** | `boolean` |
| **WirelessMode** | `number` |
| **ZoneName** | `string` |
