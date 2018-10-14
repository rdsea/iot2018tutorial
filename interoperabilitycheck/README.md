# Check interoperability of resource slice

Using [rsiHubIntOp service](https://github.com/SINCConcept/HINC/blob/master/interoperability-service/), one can check possible interoperability issues for resource slice.

 ## Running examples

 Examples are available at https://github.com/SINCConcept/HINC/tree/master/interoperability-service/client_testslices/basic

 Running pizza with intop commands such as:

 ```
 $pizza intop check 0_working_slice.json
 $pizza intop check 1_direct_mismatch.json
 $pizza intop check 2_indirect_mismatch.json

```
