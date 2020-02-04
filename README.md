# nat-pmp-for-cisco
A quick hack to make NAT-PMP work with my Cisco 891 router

# draft design

Run this in a VM.

First step is to setup a Linux server with [miniupnpd](https://github.com/miniupnp/miniupnp).
miniupnp will receive NAT-PMP requests and know about them.

Then, get the port-forwarding information and maintain a state: { time added, lifetime, external port, internal host, internal port, description }

Make this state evolve as miniupnpd handles it.

As this state evolves, publish the changes as a set of Cisco commands sent over the console.

# "sort of ideal" yet hackish design

Add a "hooks" handler to miniupnpd to allow a script-based implementation of NAT-PMP to be realized, and submit this to the miniupnpd upstream.

# best design

use a home router at home.
