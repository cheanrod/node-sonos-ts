---
layout: default
title: GroupManagementService
parent: Services
grand_parent: Sonos device
---
# GroupManagementService
{: .no_toc }

```js
const SonosDevice = require('@svrooij/sonos').SonosDevice
const sonos = new SonosDevice('192.168.x.x')
sonos.GroupManagementService.OneOfTheMethodsBelow({...})
```

All methods that require input expect an object with the specified parameters, even if it only requires one parameter.

1. TOC
{:toc}

---

### AddMember

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **MemberID** | `string` |  |
| **BootSeq** | `number` |  |

Output:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentTransportSettings** | `string` |  |
| **CurrentURI** | `string` |  |
| **GroupUUIDJoined** | `string` |  |
| **ResetVolumeAfter** | `boolean` |  |
| **VolumeAVTransportURI** | `string` |  |

### RemoveMember

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **MemberID** | `string` |  |

### ReportTrackBufferingResult

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **MemberID** | `string` |  |
| **ResultCode** | `number` |  |

### SetSourceAreaIds

Input:

| parameter | type | description |
|:----------|:-----|:------------|
| **DesiredSourceAreaIds** | `string` |  |

## GroupManagementService event

```js
const SonosDevice = require('@svrooij/sonos').SonosDevice
const sonos = new SonosDevice('192.168.x.x')
sonos.GroupManagementService.Events('serviceEvent', (data) => {
  console.log(data);
});
```

The **GroupManagementService** emits events with these properties. Not all properties are emitted everytime.

| parameter | type |
|:----------|:-----|
| **GroupCoordinatorIsLocal** | `boolean` |
| **LocalGroupUUID** | `string` |
| **ResetVolumeAfter** | `boolean` |
| **SourceAreaIds** | `string` |
| **VirtualLineInGroupID** | `string` |
| **VolumeAVTransportURI** | `string` |
