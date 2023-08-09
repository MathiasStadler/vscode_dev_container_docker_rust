# TESTED ON - 08.2023

## hardware

```bash
uname -a |sed 's/ /\n/g'|sed 's/#//g'
```

Linux\
ThinkPad-T430\
5.19.0-50-generic\
50-Ubuntu\
SMP\
PREEMPT_DYNAMIC\
Mon Jul 10 18:24:29 UTC 2023\
x86_64\
x86_64\
x86_64\
GNU/Linux\

## os version

```bash
ubuntu-report show
```

{
  "Version": "22.04",
  "OEM": {
    "Vendor": "LENOVO",
    "Product": "23501B6",
    "Family": "ThinkPad T430"
  },
  "BIOS": {
    "Vendor": "LENOVO",
    "Version": "G1ET93WW (2.53 )"
  },
  "Arch": "amd64",
  "HwCap": "x86-64-v2",
  "GPU": [
    {
      "Vendor": "8086",
      "Model": "0166"
    }
  ],
  "RAM": 16,
  "Disks": [
    512.1,
    128
  ],
  "Partitions": [
    122,
    0.5
  ],
  "Autologin": false,
  "LivePatch": false,
  "Session": {
    "DE": "Unity",
    "Name": "ubuntu-xorg",
    "Type": "x11"
  },
  "Language": "de_DE",
  "Timezone": "Europe/Berlin",
  "Install": {
    "Media": "Ubuntu 20.04.1 LTS \"Focal Fossa\" - Release amd64 (20200731)",
    "Type": "GTK",
    "OEM": false,
    "PartitionMethod": "use_device",
    "DownloadUpdates": true,
    "Language": "en",
    "Minimal": false,
    "RestrictedAddons": false,
    "Stages": {
      "0": "language",
      "1": "language",
      "15": "console_setup",
      "36": "console_setup",
      "44": "prepare",
      "75": "partman",
      "146": "partman",
      "165": "partman",
      "167": "partman",
      "175": "start_install",
      "190": "timezone",
      "193": "usersetup",
      "221": "user_done",
      "628": "done"
    }
  },
  "Upgrade": {
    "From": "20.04",
    "InstallMedia": "Ubuntu 20.04.1 LTS \"Focal Fossa\" - Release amd64 (20200731)",
    "Type": "Text",
    "ThirdPartySources": false,
    "Stages": {
      "0": "start",
      "2": "PREPARE",
      "16": "MODIFY_SOURCES",
      "136": "FETCH",
      "252": "INSTALL",
      "256": "INSTALL",
      "352": "INSTALL",
      "1025": "POSTUPGRADE",
      "1125": "CLEANUP",
      "1274": "REBOOT"
    }
  }
}
