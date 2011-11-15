= DESCRIPTION:

XXX: This is a cookbook allowing custom iptable rules to be defined
outside of the normal methods. This allows rules to be defined when
the original cookbook doesn't define iptables rules or there is no
cookbook (for example, ssh).

= REQUIREMENTS:

= ATTRIBUTES:

 - node[:firewall][:port_scan_ssh] = { :window => 5,
                                       :max_conns => 20,
                                       :port => 22
                                     }

   The recipe 'firewall::port_scan' will search for all properties
   named 'node[:firewall][:port_scan_*]'. This will create a rule that
   allows only ':max_conns' connections with a window period of ':window'
   seconds. For example, the settings above state that a maximum of 20
   connections can be made to the ssh port (22) within a period of 5
   seconds. If any more than that are made within 5 seconds, the
   source will automatically be dropped.

= USAGE:

  include_recipe 'firewall::port_scan'