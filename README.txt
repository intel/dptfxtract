Linux DPTF Extract Utility

This is a companion tool to Linux Thermal Daemon (thermald). This tool tries to reuse some of the tables used by
"Intel ® Dynamic Platform and Thermal Framework (Intel® DPTF)" by converting to the thermal_conf.xml format used by thermald.

There are two ways this tool can be used:
- Execute on the same system as thermald
In this mode root privilege is required. This tool will copy converted files to /var/run/thermald/ folder. This is the default folder for thermald to pickup auto generated configuration file using ACPI tables.

- Execute on existing output of Linux acpidump utilities
In this mode the existing ACPI dump is parsed and output file is generated and copied to /var/run/thermald/. For example to generate acpi dump and create thermal_conf.xml manually:
# acpidump > acpi.out
# acpixtract -a acpi.out
# dptfxtract "*.dat"

Refer to COPYING file for the license information.

Security / Vulnerability Reporting
Refer to https://01.org/security for submission instructions.
