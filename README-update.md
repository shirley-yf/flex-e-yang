A tree diagram of FlexE group:

module: ietf-flexe-cm
   +--rw flexe
      +--rw flexe-groups
         +--rw flexe-group* [group-index]
            +--rw index              uint32
            +--rw group-num          uint32
            +--rw negotiation-mode   negotiation-mode-type
            +--ro total-bandwidth    string
            +--ro free-bandwidth?    string
            +--ro sync-phy-number    uint32
            +--rw flexe-phys
               +--rw flexe-phy-list* [port-name]
                   +--rw port-name        if:interface-ref
                   +--rw phy-number       uint32
                   +--ro free-timeslot-list  string
                   +--ro used-timeslot-list  string

A tree diagram of FlexE client:

augment /if:interfaces/if:interface:
    +--rw flexe-client
       +--rw client-index         uint32
       +--rw group-index          leafref
       +--rw client-num           uint32
       +--rw timeslot-lists
          +--rw timeslot-list*    [port-name]
             +--rw port-name      if:interface-ref
             +--rw time-slot      string
