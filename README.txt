Linux DPTF Extract Utility

[
Thermald version 2.0 and later has in built parser for thermal tables. So this utility is not required.
Make sure that thermald "--adaptive" option is used.
]

This is a companion tool to Linux Thermal Daemon (thermald). This tool tries to reuse some of the tables used by
"Intel ® Dynamic Platform and Thermal Framework (Intel® DPTF)" by converting to the thermal_conf.xml format used by thermald.

There are two ways this tool can be used:
- Execute on the same system as thermald
In this mode root privilege is required. This tool will copy converted files to /etc/thermald/ folder. This is the default folder for thermald to pickup auto generated configuration file using ACPI tables.

- Execute on existing output of Linux acpidump utilities
In this mode the existing ACPI dump is parsed and output file is generated and copied to /etc/thermald/. For example to generate acpi dump and create thermal_conf.xml manually:
# acpidump > acpi.out
# acpixtract -a acpi.out
# dptfxtract *.dat

- In some systems there can be multiple configuration files. For example
thermal-conf.xml.0
thermal-conf.xml.1
thermal-conf.xml.auto

The Linux thermald by default uses thermal-conf.xml.auto. But if the other configurations are better suited for a use case, then thermald option --config-file, can be used to pick a different configuration file.

dptfxtract-static has the same functionality as dptfxtract, except it is linked statically.


Refer to COPYING file for the license information.

Security / Vulnerability Reporting
Refer to https://01.org/security for submission instructions.
