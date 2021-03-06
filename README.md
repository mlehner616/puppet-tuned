# puppet-tuned

## Overview

Install, enable and configure the tuned adaptive system tuning daemon found in
Red Hat Enterprise Linux.

* `tuned` : Class to install and enable tuned

## Examples

Install and enable tuned with the ''default'' profile :

    include tuned

Install and enable tuned with the ''virtual-host'' profile :

    class { 'tuned': profile => 'virtual-host' }

Check the output of `tuned-adm list` to see the available profiles on your
systems.

Install and enable tuned with a custom profile, contained in another module :

    class { 'tuned':
      profile => 'my-super-tweaks',
      source  => 'puppet:///modules/mymodule/tune-profiles/my-super-tweaks',
    }

To completely disable and remove a previously configured tuned :

    class { 'tuned': ensure => absent }

