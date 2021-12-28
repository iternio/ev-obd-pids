# EV-OBD-PIDs
This repository contains a consolidation of the various OBD PID lists that are available openly on the internet for Electric Vehicles, formatted such that they can be imported by A Better Routeplanner's OBD integration. 

Many thanks to the hard work by those who have reverse engineered the PIDs for various manufacturers and contributed to this repository.

## Adding Support
If you'd like to add your own PID list here please submit a pull request to the repository.  We have support for equation parsing similar to Torque Pro (and more can be added if needed).

### Structure of the PID List:
- `init_commands` - List of commands sent to initialize the OBD dongle.  
- `obd_protocol` - Which OBD protocol is used by your car. Typically 6 or 7 from our experience.  
- `data_commands` - A list of unique OBD commands, these will be sent in order with the results passed to all matching PIDs and their formulas.  
- All other entries are the individual PIDs, and their keys (names) must match those in the [Telemetry API documentation](https://documenter.getpostman.com/view/7396339/SWTK5a8w).

### Supported equations
| Equation Element| Description |
| --- | --- |
| A - ZZZ | Data value from a PID request |
| *, /, +, - | Multiplication, Division, Addition, Subtraction |
| \|\| | Logical Or|
| && | Logical And |
| == | Logical Equals|
| <,> | Logical Less/Greater Than |
| <=,>= | Logical Less/Greater Than Equals |
| <<, >> | Bitwise shift operators, shift the binary value the specified number of spaces left or right |
| Signed(#) | Treats # as an 8bit signed |
| Int16(A,B) | Converts A & B to a 16-bit Int (A*256 + B) |
| Int24(A,B,C) | Converts A, B, & C to a 24-bit Int (A\*65536 + B\*256 + C) |
| {A:#} | #th bit of byte A from right (least significant digit) |
## Licenses
This repository is licensed by Apache 2.0, except where superceded by individual licenses from the various sources.  A LICENSE file will be placed in any sub-directory where applicable.

## WARNING

THESE PID LISTS ARE PROVIDED AS IS. USE THE SOFTWARE AT YOUR OWN RISK. THE AUTHORS MAKE NO WARRANTIES AS TO PERFORMANCE OR FITNESS FOR A PARTICULAR PURPOSE, OR ANY OTHER WARRANTIES WHETHER EXPRESSED OR IMPLIED. NO ORAL OR WRITTEN COMMUNICATION FROM OR INFORMATION PROVIDED BY THE AUTHORS SHALL CREATE A WARRANTY. UNDER NO CIRCUMSTANCES SHALL THE AUTHORS BE LIABLE FOR DIRECT, INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES RESULTING FROM THE USE, MISUSE, OR INABILITY TO USE THE SOFTWARE, EVEN IF THE AUTHOR HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. THESE EXCLUSIONS AND LIMITATIONS MAY NOT APPLY IN ALL JURISDICTIONS. YOU MAY HAVE ADDITIONAL RIGHTS AND SOME OF THESE LIMITATIONS MAY NOT APPLY TO YOU. THIS SOFTWARE IS ONLY INTENDED FOR SCIENTIFIC USAGE.
