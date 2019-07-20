## Course Header

Size 0x200.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x1  | Start Y Position |
| 0x1    | 0x1  | Goal Y Position |
| 0x2    | 0x2  | Goal X Position |
| 0x4    | 0x2  | Time Limit |
| 0x6    | 0x2  | Clear Condition Amount |
| 0x8    | 0x2  | Creation Year |
| 0xA    | 0x1  | Creation Month |
| 0xB    | 0x1  | Creation Day |
| 0xC    | 0x1  | Creation Hour |
| 0xD    | 0x1  | Creation Minute |
| 0xE    | 0x1  | Custom Scroll Speed (0=x1, 1=x2, 2=x3) |
| 0xF    | 0x1  | Clear Condition Type (1=Parts, 2=Status, 3=Actions) |
| 0x10   | 0x4  | Clear Condition CRC32 |
| 0x14   | 0x4  | Course Game Version Built (1=1.0.0, 2=1.0.1, 3=Unknown) |
| 0x18   | 0x4  | Management Flags (bit0=Always set, except for quest_105 and quest_115. bit1=Has completed course, bit4=Cant upload course, bit5=Has clear condition amount, bit6=Has chosen sub area orientation. bit2 and bit7 are unseen, bit3 is used only for Lesson and Quest courses) |
| 0x1C   | 0x4  | Number of Clear Check Tries |
| 0x20   | 0x4  | Clear Check Time |
| 0x24   | 0x4  | Creation ID |
| 0x28   | 0x8  | Upload ID |
| 0x30   | 0x4  | Unknown Flag |
| 0x34   | 0xBC | Padding |
| 0xF0   | 0x1  | Unknown, usually FF |
| 0xF1   | 0x3  | Game Type (M1, M3, MW, WU, 3W) |
| 0xF4   | 0x42 | Course Name, 32 characters, null-terminated |
| 0x136  | 0xCA | Course Description, 75 characters with space for 100, null-terminated |
