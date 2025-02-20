# NCAP Scenarios modelled in OpenSCENARIO

[Euro NCAP](https://www.euroncap.com/) provides descriptions of collision scenarios to test active safety systems of vehicles. Prior to conducting these tests on a test track, virtual test drives can provide valuable insights during the development of new driver assistance systems. Therefore, the scenarios must be described in a machine-readable format. [ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [ASAM OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) are open standards defining such formats. Scenario descriptions based on these standards serve as input to standard-compliant simulators like [Vector DYNA4](https://www.vector.com/dyna4). As the [Euro NCAP](https://www.euroncap.com/) scenarios are widely used, Vector decided to contribute the implementation of these scenarios using the ASAM standards. The goal is to foster the community trend for shift left testing with virtual test drives and ultimately make roads safer.

## Euro NCAP Test Protocols

The following protocols have served as a basis for the implementation of the scenarios:

- [Euro NCAP Test Protocol – AEB/LSS VRU systems, Implementation 2023, Version 4.5.1, February 2024](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf)
- [Euro NCAP Test Protocol – AEB Car-to-Car systems, Implementation 2023, Version 4.3.1, February 2024](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf)

## [ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [ASAM OpenDRIVE](https://www.asam.net/standards/detail/opendrive/)

[ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) defines an XML-based file format for the description of the dynamic part of scenarios like the movement of traffic participants or environmental conditions such as weather. Using parameters instead of concrete values, [ASAM OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) enables the automatic variation of scenarios, a vital feature for the modelling of the [Euro NCAP](https://www.euroncap.com/) scenarios as similar scenarios are performed at different speeds etc. Scenarios within a parameter space are often referred to as 'logical scenarios' in contrast to 'concrete scenarios' that use a specific set of concrete parameter values.

[ASAM OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) defines an XML-based file format for the description of the static part of scenarios including the road network and nearby objects such as traffic signals or buildings. OpenDRIVE files are referenced by the OpenSCENARIO files. Although the road networks used for the [Euro NCAP](https://www.euroncap.com/) scenarios are rather simple, they have been auto-generated using the [Python 'scenariogeneration' package](https://pypi.org/project/scenariogeneration/) for better maintainability.

## Usage

You only need to clone the repository to get the OpenSCENARIO XML and OpenDRIVE files and essentially you're ready to start simulating with your preferred standard-compliant simulator. However, the following notes on the usage should be considered:

- Some of the scenarios defined by [Euro NCAP](https://www.euroncap.com/) are very similar, which is why some of the NCAP scenarios share the same concrete OpenSCENARIO definition, in the table below referred to as 'XOSC Base Scenario'. The differences are only achieved by a parameter variation through the logical scenario features of OpenSCENARIO XML (see section above). The same holds true for the variation of the parameters such as the vehicle speed according to the NCAP protocols. Variation files are included that enable a single execution of each NCAP scenario or the full variation of all values as described by [Euro NCAP](https://www.euroncap.com/). The provided scenarios are listed in the table below and it is indicated, which base scenario is used. Stay tuned as we prepare more scenarios.

|NCAP Scenario |NCAP Protocol |XOSC Base Scenario |
| --- | --- | --- |
| **Car-to-Pedestrian Farside Adult 50% (CPFA-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CPNA-25 |
| **Car-to-Pedestrian Nearside Adult 25% (CPNA-25)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CPNA-25 |
| **Car-to-Pedestrian Nearside Adult 75% (CPNA-75)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CPNA-25 |
| **Car-to-Pedestrian Nearside Child Obstructed 50% (CPNCO-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CPNCO-50 |
| **Car-to-Pedestrian Longitudinal Adult 25% (CPLA-25)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CBLA-50 |
| **Car-to-Pedestrian Longitudinal Adult 50% (CPLA-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CBLA-50 |
| **Car-to-Pedestrian Reverse Adult/Child moving 50% (CPRA/Cm-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CPRA/Cm-50 |
| **Car-to-Pedestrian Reverse Adult/Child stationary (CPRA/Cs)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CPRA/Cs |
| **Car-to-Pedestrian Turning Adult 50% (CPTA-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CPTA-50 |
| **Car-to-Bicyclist Nearside Adult 50% (CBNA-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CBNA-50 |
| **Car-to-Bicyclist Nearside Adult Obstructed 50% (CBNAO-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CBNAO-50 |
| **Car-to-Bicyclist Farside Adult 50% (CBFA-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CBFA-50 |
| **Car-to-Bicyclist Longitudinal Adult 25% (CBLA-25)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CBLA-50 |
| **Car-to-Bicyclist Longitudinal Adult 50% (CBLA-50)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CBLA-50 |
| **Car-to-Motorcyclist Front Turn Across Path (CMFtap)** | [AEB/LSS VRU systems v4.5.1](https://www.euroncap.com/media/80156/euro-ncap-aeb-lss-vru-test-protocol-v451.pdf) | CCFtap |
| **Car-to-Car Front Head-On Lane change (CCFhol)** | [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | CCFhol |
| **Car-to-Car Front Head-On Straight (CCFhos)** | [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | CCFhos |
| **Car-to-Car Front Turn-Across-Path (CCFtap)** | [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | CCFtap |
| **Car-to-Car Rear Stationary (CCRs)** | [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | CCRs |
| **Car-to-Car Rear Moving (CCRm)** | [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | CCRs |
| **Car-to-Car Rear Braking (CCRb)** | [AEB Car-to-Car systems v4.3.1](https://www.euroncap.com/media/80155/euro-ncap-aeb-c2c-test-protocol-v431.pdf) | CCRs |

- OpenSCENARIO XML in version 1.3 is used as certain features like 'ClothoidSpline' for the description of trajectories for turning maneuvers are required. Other updates on the standard are incorporated as well such as the absence of 'StartTrigger' elements where applicable. In short: **your simulator must support OpenSCENARIO XML 1.3 to be able to use the provided scenarios**.
- For scenarios in which the ego vehicle turns, [Euro NCAP](https://www.euroncap.com/) specifies a trajectory to be followed. While the OpenSCENARIO XML feature 'ClothoidSpline' allows to describe such trajectories, OpenSCENARIO specifies the center of the rear axle as the control point to follow these trajectories. [Euro NCAP](https://www.euroncap.com/) however specifies the center of the front axle as the control point. Therefore, the affected scenarios contain a proprietary yet standard-conform key-value pair within a 'Controller' to adjust the control point to the center of the front axle. As of now, this key-value pair is only interpreted by [Vector DYNA4](https://www.vector.com/dyna4) but may be standardized in a similar way within future versions of OpenSCENARIO XML.

### Notes for users of [Vector DYNA4](https://www.vector.com/dyna4)

- We recommend to use DYNA4 Release 9 Service Pack 1.
- DYNA4 already comes with an example project 'Demo_NCAP'. The most important differences of the files in this repository compared to the DYNA4 delivery are as follows:
  - relative paths between files are used instead of DYNA4 database paths using DYNA4's content management prefix
  - Vehicle Catalog and Pedestrian Catalog contain only entities that are used within the scenarios of this repository
  - Vehicle Catalog and Pedestrian Catalog are contained in the 'NCAP/Catalogs' folder instead of the 'OpenSCENARIO/Catalogs' folder
  - entities in 'VehicleCatalog' and 'PedestrianCatalog' do not reference a 3D model for visualization
- The files in this repository may be updated independently of DYNA4 releases. To use any updates in this repository that are not yet included in your DYNA4 release version we recommend to:
  - Generate a new and unmodified instance of the Demo_NCAP example project.
  - Overwrite the folder contents of OpenSCENARIO and OpenDRIVE in the simulation project's database with the contents from this repository.
  - Create new Scenarios and Tasks for any NCAP scenarios that are newly covered compared to your DYNA4 release version.
  - You may want to change the 'CatalogLocations' of 'VehicleCatalog' and 'PedestrianCatalog' in each XOSC back to 'OpenSCENARIO/Catalogs/Vehicles' and 'OpenSCENARIO/Catalogs/Pedestrians', respectively, to get a proper visualization of the entities with the 3D models from the DYNA4 animation database.

## Citation

If you want to refer to this work in publications, please cite "Automated NCAP tests with ASAM OpenSCENARIO"; Jakob Kaths, Benedikt Schott, Hannah Bernauer, Markus Pielmeier, André Pinnel. AutoTest Technical Conference, 2024.

## Legal

The [OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) files have been licensed under [MPL-2.0](https://www.mozilla.org/en-US/MPL/2.0/) and are hereby made publicly available.

The scenarios have been implemented by Vector with great care based on the textual descriptions in the [Euro NCAP](https://www.euroncap.com/) protocols to our best knowledge. However, Vector is not liable for the correctness and completeness of the [OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) files.

The XSD schemas of [OpenSCENARIO XML](https://www.asam.net/standards/detail/openscenario-xml/) and [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) are under the license of ASAM, which can be found within the respective standard document.

At the moment, we do not accept external contributions until we have established a contribution process, see [CONTRIBUTING.md](CONTRIBUTING.md) for further details.
