# gNMI Set

A simple shell binary that performs a SET against a gNMI Target.

## Install

```
go get github.com/dzhangalibaba/gnxi/gnmi_set
go install github.com/dzhangalibaba/gnxi/gnmi_set
```

## Run

Run gnmi\_set -help to see usage. For example:

```
/gnmi_set -xpath_target CONFIG_DB -update BGP_NEIGHBOR/10.0.0.9/route_map_in:AS_Overwrite -target_addr localhost:8080 -alsologtostderr -insecure true
== setRequest:
prefix: <
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
      name: "route_map_in"
    >
  >
  val: <
    string_val: "AS_Overwrite"
  >
>

== getResponse:
prefix: <
  target: "CONFIG_DB"
>
response: <
  path: <
    elem: <
      name: "BGP_NEIGHBOR"
    >
    elem: <
      name: "10.0.0.9"
    >
    elem: <
      name: "route_map_in"
    >
  >
  op: UPDATE
>
timestamp: 1481283124751187994

```
