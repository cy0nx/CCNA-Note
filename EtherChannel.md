SW(config) port-channel load-balance mode
##configures the EtherChannel load-balancing method on the switch

SW# show etherchannel load-balance
##displays information about the load-balancing settings

![[2 1.png]]

SW(config-if)# channel-group number mode {desirable|auto|active|passive|on}
##configures an interface to be part of an EtherChannel

![[3.png]]

SW# show etherchannel summary
##displays a summary of EtherChannels on the switch

SW# show etherchannel port-channel
##displays information about the virtual port-channel interfaces on the switch

![[1445-06-30 13_14_53-Free CCNA _ EtherChannel _ Day 23 _ CCNA 200-301 Complete Course - YouTube.png]]
