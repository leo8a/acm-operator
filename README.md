# Ansible Role: ACM operator

[![CI](https://github.com/leo8a/acm-operator/actions/workflows/ci.yml/badge.svg)](https://github.com/leo8a/acm-operator/actions/workflows/ci.yml)

Installs the [ACM](https://github.com/stolostron/deploy#deploy-the-open-cluster-management-project.git) operator on OpenShift clusters.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    acm_operator_namespace: "open-cluster-management"
    metal3:
        watch_all_namespaces: true

## Dependencies

This role requires the `kubernetes.core` collection, and have been tested on an OpenShift cluster version 4.10.

## Example Playbook

    - hosts: localhost
      gather_facts: false
      roles:
        - leo8a.acm_operator

To enable BMO to watch resources in all namespaces, the `watch_all_namespaces` var can be adjusted as follows:

    - hosts: localhost
      gather_facts: false
      roles:
        - leo8a.acm_operator
      vars:
        - catalog_source: "redhat-operator-index"
        - metal3:
            watch_all_namespaces: true

## License

This role is released under the Apache 2.0 license. See the [LICENSE](LICENSE).

## Author Information

This role was created in 2022 by [Leo Ochoa](https://github.com/leo8a/).

## Contributors

This is the current list of folks in the `acm_operator` hall of ~~fame~~ contributors 🏆!

<a href="https://github.com/leo8a/acm-operator/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=leo8a/acm-operator"  alt=""/>
</a>

> Made with [contributors-img](https://contrib.rocks).
