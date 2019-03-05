# gNMI Get

A simple shell binary that performs a GET against a gNMI Target.

## Install

```
go get github.com/dzhangalibaba/gnxi/gnmi_get
go install github.com/dzhangalibaba/gnxi/gnmi_get
```

## Run

```
gnmi_get \
  -xpath_target CONFIG_DB
  -xpath "/system/openflow/agent/config/datapath-id" \
  -xpath "/system/openflow/controllers/controller[name=main]/connections/connection[aux-id=0]/state/address" \
  -target_addr localhost:10161 \
  -target_name hostname.com \
  -key client.key \
  -cert client.crt \
  -ca ca.crt \
  -username foo \
  -password bar \
  -alsologtostderr
```
```
./gnmi_get -xpath_target CONFIG_DB -xpath BGP_NEIGHBOR/10.0.0.9/name -target_addr localhost:8080 -alsologtostderr -insecure true
== getRequest:
prefix: <
  target: "CONFIG_DB"
>
path: <
  elem: <
    name: "BGP_NEIGHBOR"
  >
  elem: <
    name: "10.0.0.9"
  >
  elem: <
    name: "name"
  >
>
encoding: JSON_IETF

== getResponse:
notification: <
  timestamp: 1481282910872378151
  prefix: <
    origin: "PSW-7005"
    target: "CONFIG_DB"
  >
  update: <
    path: <
      elem: <
        name: "BGP_NEIGHBOR"
      >
      elem: <
        name: "10.0.0.9"
      >
      elem: <
        name: "name"
      >
      target: "CONFIG_DB"
    >
    val: <
      string_val: "ASW2"
    >
  >
>

```
