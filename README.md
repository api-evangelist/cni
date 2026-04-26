# Container Network Interface (cni)

CNI (Container Network Interface) is a CNCF-incubating project that defines a specification and libraries for configuring network interfaces in Linux containers. It provides a simple exec/stdin interface between the container runtime and network implementation plugins, enabling pluggable networking for Kubernetes and other container orchestrators. The CNI spec defines four operations (ADD, DEL, CHECK, VERSION), a network configuration document, and a plugin Result document. CNI also publishes reference plugins (bridge, ipvlan, macvlan, host-device, ptp, loopback) and meta-plugins (portmap, bandwidth, firewall, sbr).

**URL:** [https://raw.githubusercontent.com/api-evangelist/cni/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/cni/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **x-type:** opensource
- **Access:** 3rd-Party

## Tags

- Cloud Native
- Containers
- Incubating
- Kubernetes
- Networking
- Plugins

## Timestamps

- **Created:** 2026-03-16
- **Modified:** 2026-04-23

## APIs

### CNI Specification

The CNI specification defines the interface between container runtimes and network plugins. It specifies how runtimes invoke plugins via environment variables (CNI_COMMAND, CNI_CONTAINERID, CNI_NETNS, CNI_IFNAME, CNI_PATH, CNI_ARGS) and stdin configuration, and how plugins respond on stdout with network interface details.

**Human URL:** [https://www.cni.dev/docs/spec/](https://www.cni.dev/docs/spec/)

#### Tags

- Network Plugins, Specification

#### Properties

- [Documentation](https://www.cni.dev/docs/spec/)
- [GitHub Repository](https://github.com/containernetworking/cni)
- [Network Config JSON Schema](json-schema/cni-network-config-schema.json)
- [Result JSON Schema](json-schema/cni-result-schema.json)
- [JSON-LD Context](json-ld/cni-context.jsonld)
- [Naftiko Capabilities](capabilities/cni-spec-capabilities.yml)

#### Features

- **ADD operation:** Attach a container to a network and return a Result document.
- **DEL operation:** Detach a container from a network and tear down resources.
- **CHECK operation:** Verify the container's current attachment matches the prior ADD result.
- **VERSION operation:** Report the CNI spec versions a plugin supports.
- **Plugin Chaining:** Meta-plugin chaining with prevResult.
- **Network Config Schema:** JSON document describing a network and its plugin chain.
- **Result Schema:** JSON document plugins emit on stdout.

#### Use Cases

- **Kubernetes CNI Plugin:** Implement a CNI plugin that integrates with Kubernetes / containerd / CRI-O.
- **Network Validation:** Validate network configurations and plugin Result documents against the spec.
- **Custom SDN:** Build custom software-defined networks for containers using a portable plugin contract.

### CNI Reference Plugins

A collection of reference networking plugins (bridge, ipvlan, macvlan, ptp, host-device, loopback) and meta-plugins (portmap, bandwidth, firewall, sbr, tuning) maintained by the containernetworking team.

**Human URL:** [https://www.cni.dev/plugins/current/](https://www.cni.dev/plugins/current/)

#### Tags

- Containers, Kubernetes, Linux, Network Plugins, Networking

#### Properties

- [Documentation](https://www.cni.dev/plugins/current/)
- [GitHub Repository](https://github.com/containernetworking/plugins)
- [Naftiko Capabilities](capabilities/cni-spec-capabilities.yml)

## Common Properties

- [Website](https://www.cni.dev/)
- [Documentation](https://www.cni.dev/docs/)
- [GitHub Organization](https://github.com/containernetworking)
- [Network Config JSON Schema](json-schema/cni-network-config-schema.json)
- [Result JSON Schema](json-schema/cni-result-schema.json)
- [JSON-LD Context](json-ld/cni-context.jsonld)
- [Naftiko Capabilities](capabilities/cni-spec-capabilities.yml)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
