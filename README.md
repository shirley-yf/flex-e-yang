# flex-e-yang
Flex-e YANG model structure

```
module: ietf-if-flex-e
  augment /if:interfaces/if:interface:
    +--rw flex-e
       +--rw group-number              uint32
       +--rw more-group-config-here?   string
       +--rw bonded-phy* [name]
       |  +--rw name                           if:interface-ref
       |  +--rw phy-number?                    uint8
       |  +--rw more-bonded-phy-config-here?   string
       +--rw client-interface* [name]
          +--rw name                              if:interface-ref
          +--rw id?                               uint16
          +--rw more-flex-e-client-config-here?   string
```
