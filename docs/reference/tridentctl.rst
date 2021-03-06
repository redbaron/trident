##########
tridentctl
##########

The `Trident installer bundle`_ includes a command-line utility, ``tridentctl``,
that provides simple access to Trident. It can be used to install Trident, as
well as to interact with it directly by any Kubernetes users with sufficient
privileges, to manage the namespace that contains the Trident pod.

.. _Trident installer bundle: https://github.com/NetApp/trident/releases

For full usage information, run ``tridentctl --help``. Here are the available
commands and global options:

.. code-block:: console

  Usage:
    tridentctl [command]

  Available Commands:
    create      Add a resource to Trident
    delete      Remove one or more resources from Trident
    get         Get one or more resources from Trident
    help        Help about any command
    install     Install Trident
    logs        Print the logs from Trident
    uninstall   Uninstall Trident
    update      Modify a resource in Trident
    version     Print the version of Trident

  Flags:
    -d, --debug              Debug output
    -h, --help               help for tridentctl
    -n, --namespace string   Namespace of Trident deployment
    -o, --output string      Output format. One of json|yaml|name|wide|ps (default)
    -s, --server string      Address/port of Trident REST interface

create
------

Add a resource to Trident

.. code-block:: console

  Usage:
    tridentctl create [command]

  Available Commands:
    backend     Add a backend to Trident

delete
------

Remove one or more resources from Trident

.. code-block:: console

  Usage:
    tridentctl delete [command]

  Available Commands:
    backend      Delete one or more storage backends from Trident
    storageclass Delete one or more storage classes from Trident
    volume       Delete one or more storage volumes from Trident

get
---

Get one or more resources from Trident

.. code-block:: console

  Usage:
    tridentctl get [command]

  Available Commands:
    backend      Get one or more storage backends from Trident
    storageclass Get one or more storage classes from Trident
    volume       Get one or more volumes from Trident

install
-------

Install Trident

.. code-block:: console

  Usage:
    tridentctl install [flags]

  Flags:
        --dry-run                   Run all the pre-checks, but don't install anything.
        --etcd-image string         The etcd image to install.
        --generate-custom-yaml      Generate YAML files, but don't install anything.
    -h, --help                      help for install
        --k8s-timeout duration      The number of seconds to wait before timing out on Kubernetes operations. (default 3m0s)
        --pv string                 The name of the PV used by Trident.
        --pvc string                The name of the PVC used by Trident.
        --silent                    Disable most output during installation.
        --trident-image string      The Trident image to install.
        --ucp-bearer-token string   UCP authorization token (for Docker UCP only).
        --ucp-host string           IP address of the UCP host (for Docker UCP only).
        --use-custom-yaml           Use any existing YAML files that exist in setup directory.
        --volume-name string        The name of the storage volume used by Trident.
        --volume-size string        The size of the storage volume used by Trident. (default "2Gi")

logs
----

Print the logs from Trident

.. code-block:: console

  Usage:
    tridentctl logs [flags]

  Flags:
    -a, --archive      Create a support archive with all logs unless otherwise specified.
    -h, --help         help for logs
    -l, --log string   Trident log to display. One of trident|etcd|auto|all (default "auto")
    -p, --previous     Get the logs for the previous container instance if it exists.

uninstall
---------

Uninstall Trident

.. code-block:: console

  Usage:
    tridentctl uninstall [flags]

  Flags:
    -a, --all                       Deletes almost all artifacts of Trident, including the PVC and PV used by Trident;
                                    however, it doesn't delete the volume used by Trident from the storage backend. Use with caution!
    -h, --help                      help for uninstall
        --silent                    Disable most output during uninstallation.
        --ucp-bearer-token string   UCP authorization token (for Docker UCP only).
        --ucp-host string           IP address of the UCP host (for Docker UCP only).

update
------

Modify a resource in Trident

.. code-block:: console

  Usage:
    tridentctl update [command]

  Available Commands:
    backend     Update a backend in Trident

version
-------

Print the version of tridentctl and the running Trident service

.. code-block:: console

  Usage:
    tridentctl version
