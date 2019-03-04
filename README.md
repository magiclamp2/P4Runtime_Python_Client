# P4Runtime Python Client

- Brief Intro
    - `Client.py` is the main program and `basic.py` is for library.
    - You can simply run `client.py` as a client.
    - Alternatively, you can intergrate `client.py` into other program and call functions in `basic.py`

- Usage:
```
usage: client.py [-h] --device {tofino,bmv2} --p4info P4INFO [--config CONFIG]
                 [--ctx-json CTX_JSON] [--grpc-addr GRPC_ADDR] --device-id
                 DEVICE_ID [--skip-config] [--skip-role-config] --election-id
                 ELECTION_ID [--role-id ROLE_ID]

A simple P4Runtime Client

optional arguments:
  -h, --help            show this help message and exit
  --device {tofino,bmv2}
                        Target device
  --p4info P4INFO       Location of p4info proto in text format
  --config CONFIG       Location of Target Dependant Binary
  --ctx-json CTX_JSON   Location of Context.json
  --grpc-addr GRPC_ADDR
                        Address to use to connect to P4 Runtime server
  --device-id DEVICE_ID
                        Device id for device under test
  --skip-config         Assume a device with pipeline already configured
  --skip-role-config     Assume a device do not need role config
  --election-id ELECTION_ID
                        ID for mastership election
  --role-id ROLE_ID     ID for distinguish different client
```

- Example of Usage
```
python client.py --device-id 1 --device bmv2 --grpc-addr 127.0.0.1:54717 --election-id 66 --role-id 0 \
--config "/home/sdn/onos/pipelines/basic/src/main/resources/p4c-out/bmv2/basic.json" \
--p4info "/home/sdn/onos/pipelines/basic/src/main/resources/p4c-out/bmv2/basic.p4info"
```

- Clients I found and Referenced:
    - This branch is based on the client from buck5060 for multi-tenant pipeline


- Dependence
    - PI commit: 539e4624f16aac39f8890a6dfb11c65040e735ad
    - grpc and etc.

- References:
    - [1] [P4Runtime_Python_Client](https://github.com/buck5060/P4Runtime_Python_Client.git)
    - [2] [fabric-p4test](https://github.com/opennetworkinglab/fabric-p4test)
