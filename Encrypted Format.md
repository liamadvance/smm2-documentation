## Encrypted Save Header

Size 0x10. Found at the start of an encrypted save file.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x4  | Header Index |
| 0x4    | 0x2  | Save Type (1=Quest, 8=Network, 10=Later, 11=Save, 16=Course) |
| 0x6    | 0x2  | Course Flags (0=Edited, 1=New) |
| 0x8    | 0x4  | CRC32 over decrypted file |
| 0xC    | 0x4  | Magic "SCDL" if the file is a course, empty otherwise |

In the case of save.dat, the CRC32 in the first save header is over 0x0-0xB90F, with a second save header at 0xB910 which has a CRC32 over 0xB920-0xBFBF.

## Encryption

Size 0x30. Found at the end of an encrypted save file.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x4 * 4 | AES IV |
| 0x10   | 0x4 * 4 | Random seed |
| 0x20   | 0x4 * 4 | AES-CMAC |
