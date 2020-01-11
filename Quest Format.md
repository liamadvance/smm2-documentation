The file quest.dat stores your progress for story mode.

## Course Try Data

Starts at 0x0, with a size of 0x10 * 120.

| Offset | Size | Description                                             |
|--------|------|---------------------------------------------------------|
| 0x0    | 0x4  | Try Count                                               |
| 0x4    | 0x4  | Unknown ID (Related to Course unlocking and completion) |
| 0x8    | 0x8  | Padding                                                 |

## Count Data

Starts at 0x780, with a size of 0x10.

| Offset | Size | Description                             |
|--------|------|-----------------------------------------|
| 0x0    | 0x4  | Total Try Count                         |
| 0x4    | 0x4  | Coin Count                              |
| 0x8    | 0x4  | Unknown (FF on 100% save)               |
| 0xC    | 0x4  | Unknown (Related to talking with NPCs?) |

## Castle Completion Data

Starts at 0x790, with a size of 0x10 * 16.

| Offset | Size | Description                      |
|--------|------|----------------------------------|
| 0x0    | 0x8  | Padding                          |
| 0x8    | 0x4  | Completion Amount                |
| 0xC    | 0x4  | Unknown ID (All 61 on 100% save) |

## Unknown Data

Starts at 0xAB8, with a size of 0x4.

| Offset | Size | Description             |
|--------|------|-------------------------|
| 0x0    | 0x4  | Unknown (A Size or ID?) |

## Course Completion Data

Starts at 0xB48, with a size of 0x8 * 178.

| Offset | Size | Description                                    |
|--------|------|------------------------------------------------|
| 0x0    | 0x4  | Unknown (CRC32 of course?)                     |
| 0x4    | 0x4  | Unknown (Number of Coins collected in course?) |
