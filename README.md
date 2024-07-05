# NCAP Scenarios modelled in OpenSCENARIO

[Euro NCAP](https://www.euroncap.com/) provides descriptions of collision scenarios to test active safety systems of vehicles. Prior to conducting these tests on a test track, virtual test drives can provide valuable insights during the development of new driver assistance systems. Therefore, the scenarios must be described in a machine-readable format. [ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [ASAM OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) are open standards defining such formats. Scenario descriptions based on these standards serve as input to standard-compliant simulators like [Vector DYNA4](https://www.vector.com/dyna4). As the [Euro NCAP](https://www.euroncap.com/) Scenarios are widely used, Vector decided to contribute the implementation of these scenarios using the ASAM standards. The goal is to foster the community trend for shift left testing with virtual test drives and ultimately make roads safer.

## Euro NCAP Test Protocols

The following protocols have served as a basis for the implementation of the scenarios:

- [Euro NCAP Test Protocol – AEB/LSS VRU systems, Implementation 2023, Version 4.5.1, February 2024](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf)
- [Euro NCAP Test Protocol – AEB Car-to-Car systems, Implementation 2023, Version 4.3.1, February 2024](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf)

## [ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [ASAM OpenDRIVE](https://www.asam.net/standards/detail/opendrive/)

[ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) defines an XML-based file format for the description of the dynamic part of scenarios like the movement of traffic participants or environmental conditions such as weather. Using parameters instead of concrete values, [ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) enables the automatic variation of scenarios, a vital feature for the modelling of the [Euro NCAP](https://www.euroncap.com/) scenarios as similar scenarios are performed at different speeds etc. Scenarios within a parameter space are often referred to as 'logical scenarios' in contrast to 'concrete scenarios' that use a specific set of concrete parameter values.

[ASAM OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) defines an XML-based file format for the description of the static part of scenarios including the road network and nearby objects such as traffic signals or buildings. OpenDRIVE files are referenced by the OpenSCENARIO files. Although the road networks used for the [Euro NCAP](https://www.euroncap.com/) scenarios are rather simple, they have been auto-generated using the [Python 'scenariogeneration' package](https://pypi.org/project/scenariogeneration/) for better maintainability.

## Usage

You only need to clone the repository to get the OpenSCENARIO XML and OpenDRIVE files and essentially you're ready to start simulating with your preferred standard-compliant simulator. However, the following notes on the usage should be considered:

- Some of the scenarios defined by [Euro NCAP](https://www.euroncap.com/) are very similar, which is why some of the NCAP scenarios share the same concrete OpenSCENARIO definition. The differences are only achieved by a parameter variation through the logical scenario features of OpenSCENARIO XML (see section above). The same holds true for the variation of the parameters such as the vehicle speed according to the NCAP protocols. Variation files are included that enable a single execution of each NCAP scenario or the full variation of all values as described by [Euro NCAP](https://www.euroncap.com/). The delivered scenarios are listed in the table below and it is indicated, which of these are available as a concrete scenario descriptions. Stay tuned as we prepare more scenarios.

|NCAP Protocol |NCAP Scenario |Available as concrete scenario |
| --- | --- | --- |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Pedestrian Farside Adult 50% (CPFA-50) | no |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Pedestrian Nearside Adult 25% (CPNA-25) | yes |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Pedestrian Nearside Adult 75% (CPNA-75) | no |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Pedestrian Nearside Child Obstructed 50% (CPNCO-50)  | yes |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Pedestrian Longitudinal Adult 25% (CPLA-25) | no |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Pedestrian Longitudinal Adult 50% (CPLA-50) | no |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Pedestrian Turning Adult 50% (CPTA-50) | yes |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Bicyclist Nearside Adult 50% (CBNA-50) | yes |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Bicyclist Nearside Adult Obstructed 50% (CBNAO-50) | yes |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Bicyclist Farside Adult 50% (CBFA-50) | yes |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Bicyclist Longitudinal Adult 25% (CBLA-25) | no |
| [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | Car-to-Bicyclist Longitudinal Adult 50% (CBLA-50) | yes |
| [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | Car-to-Car Rear Stationary (CCRs) | yes |
| [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | Car-to-Car Rear Moving (CCRm) | no |
| [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | Car-to-Car Rear Braking (CCRb) | no |

- OpenSCENARIO XML in version 1.3 is used as certain features like 'ClothoidSpline' for the description of trajectories for turning maneuvers are required. Other updates on the standard are incorporated as well such as the absence of 'StartTrigger' elements where applicable. In short: your simulator must support OpenSCENARIO XML 1.3 to be able to use the provided scenarios.
- For scenarios in which the ego vehicle turns, [Euro NCAP](https://www.euroncap.com/) specifies a trajectory to be followed. While the OpenSCENARIO XML feature 'ClothoidSpline' allows to describe such trajectories, OpenSCENARIO specifies the center of the rear axle as the control point to follow these trajectories. [Euro NCAP](https://www.euroncap.com/) however specifies the center of the front axle as the control point. Therefore, the affected scenarios contain a proprietary yet standard-conform key-value pair within a 'Controller' to adjust the control point to the center of the front axle. As of now, this key-value pair is only interpreted by [Vector DYNA4](https://www.vector.com/dyna4) but may be standardized in a similar way within future versions of OpenSCENARIO XML.

### Notes for users of [Vector DYNA4](https://www.vector.com/dyna4)

- As OpenSCENARIO XML 1.3 is used, DYNA4 R9 or greater needs to be used.
- DYNA4 already comes with an example project 'Demo_NCAP'. However, the files in this repository may be updated independent of DYNA4 releases. To make use of the updates here we recommend to:
  - Except for the vehicle and pedestrian catalogs overwrite the files in the DYNAdatabase and/or your Simulation Project with the ones provided in this repository.
  - Create new Scenarios and Tasks in DYNA4 in case additional NCAP scenarios are covered compared to your DYNA4 installation. Simply duplicate an existing one and load the newly added OpenSCENARIO file.

## Legal

The [OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) files have been licensed under [MPL-2.0](https://www.mozilla.org/en-US/MPL/2.0/) and are hereby made publicly available.

The scenarios have been implemented by Vector with great care based on the textual descriptions in the [Euro NCAP](https://www.euroncap.com/) protocols to our best knowledge. However, Vector is not liable for the correctness and completeness of the [OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) files.

The XSD schemas of [OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) are under the license of ASAM, which can be found within the respective standard document.

At the moment, we do not accept external contributions until we have established a contribution process, see [CONTRIBUTING.md](CONTRIBUTING.md) for further details.
