# Zustand eines Containers analysieren
Mit dem Befehl `docker inspect` können die Informationen / Werte der Container dargestellt werden.

1) Terminal öffnen
2) `docker ps -a` ausführen. Die ID des Containers kopieren, von dem man die Informartionen abfragen möchte
3) `docker inspect 88b591ae6ac8` auführen. Es erscheint folgende ausgabe:

```JSON
[
    {
        "Id": "88b591ae6ac8d9958d96d9168cfe1df0984ebf5ccf0ab7845fb5130837ec31fa",
        "Created": "2019-11-17T16:43:56.8737584Z",
        "Path": "/bin/bash",
        "Args": [],
        "State": {
            "Status": "exited",
            "Running": false,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 0,
            "ExitCode": 127,
            "Error": "",
            "StartedAt": "2019-11-17T16:43:57.5629122Z",
            "FinishedAt": "2019-11-17T17:25:08.7716227Z"
        },
        "Image": "sha256:63d7368967d836302a7f86cd485274aa1b6ee739f99390afcae0e2339ea3bdd8",
        "ResolvConfPath": "/var/lib/docker/containers/88b591ae6ac8d9958d96d9168cfe1df0984ebf5ccf0ab7845fb5130837ec31fa/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/88b591ae6ac8d9958d96d9168cfe1df0984ebf5ccf0ab7845fb5130837ec31fa/hostname",
        "HostsPath": "/var/lib/docker/containers/88b591ae6ac8d9958d96d9168cfe1df0984ebf5ccf0ab7845fb5130837ec31fa/hosts",
        "LogPath": "/var/lib/docker/containers/88b591ae6ac8d9958d96d9168cfe1df0984ebf5ccf0ab7845fb5130837ec31fa/88b591ae6ac8d9958d96d9168cfe1df0984ebf5ccf0ab7845fb5130837ec31fa-json.log",
        "Name": "/gracious_bartik",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "Capabilities": null,
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                72,
                117
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/322a04546b02f5b0451d0443be00402f5aadba4205028ba82f402161cd1a388a-init/diff:/var/lib/docker/overlay2/9de2b3a2a2833913e057acfd973ba92a53b58c87a28f8a5e76a71ab5e62d1e41/diff:/var/lib/docker/overlay2/4fe39e4b031253b3bf6ca9f740fd512fb307be28494f143d56ba564ed97c0c44/diff:/var/lib/docker/overlay2/d99c5b890a23d13edc3cb00eb93f954b2083df37f09d38d310cc3a3bf434ad9e/diff:/var/lib/docker/overlay2/9815362f10c8d925900596b683969739328e04b3b9ccc05bf72c32bbc03362f6/diff:/var/lib/docker/overlay2/325b4727b6bbbac6a31a6b0a947c1e7420c5fc61722eef73fbf18680255df5a9/diff",
                "MergedDir": "/var/lib/docker/overlay2/322a04546b02f5b0451d0443be00402f5aadba4205028ba82f402161cd1a388a/merged",
                "UpperDir": "/var/lib/docker/overlay2/322a04546b02f5b0451d0443be00402f5aadba4205028ba82f402161cd1a388a/diff",
                "WorkDir": "/var/lib/docker/overlay2/322a04546b02f5b0451d0443be00402f5aadba4205028ba82f402161cd1a388a/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "88b591ae6ac8",
            "Domainname": "",
            "User": "",
            "AttachStdin": true,
            "AttachStdout": true,
            "AttachStderr": true,
            "Tty": true,
            "OpenStdin": true,
            "StdinOnce": true,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/bin/bash"
            ],
            "Image": "ubuntu-apache2",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {}
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "08c14cba56b947fc2d52dafc7e71f9a00e39187f5f6d4f22ab4fbce8032224eb",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {},
            "SandboxKey": "/var/run/docker/netns/08c14cba56b9",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "",
            "Gateway": "",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "",
            "IPPrefixLen": 0,
            "IPv6Gateway": "",
            "MacAddress": "",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "c9e519b7fc6d9c1c4d9f2156999db534143f16843c9226a83ce660977069c96c",
                    "EndpointID": "",
                    "Gateway": "",
                    "IPAddress": "",
                    "IPPrefixLen": 0,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "",
                    "DriverOpts": null
                }
            }
        }
    }
]

```
