## Course Header

Starts at 0x0, with a size of 0x200.

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
| 0x14   | 0x4  | Course Game Version Built (bit0=1.0.0, bit1=1.0.1. Both set if the course was created in 1.0.0, and then edited in 1.0.1) |
| 0x18   | 0x4  | Management Flags (bit0=Always set, except for quest_105 and quest_115. bit1=Has completed course, bit4=Cant upload course, bit5=Has clear condition amount, bit6=Has chosen sub area orientation. bit2 and bit7 are unseen, bit3 is used only for Lesson and Quest courses) |
| 0x1C   | 0x4  | Number of Clear Check Tries |
| 0x20   | 0x4  | Clear Check Time |
| 0x24   | 0x4  | Creation ID |
| 0x28   | 0x8  | Upload ID |
| 0x30   | 0x4  | Unknown Flag |
| 0x34   | 0xBC | Padding |
| 0xF0   | 0x1  | Unknown, usually FF |
| 0xF1   | 0x3  | Game Style (M1, M3, MW, WU, 3W) |
| 0xF4   | 0x42 | Course Name, 32 characters, null-terminated |
| 0x136  | 0xCA | Course Description, 75 characters with space for 100, null-terminated |

## Course Data

Starts at 0x200, with a size of 0x48.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x1  | Course Theme (0=Ground, 1=Underground, 2=Castle, 3=Airship, 4=Underwater, 5=Ghost House, 6=Snow, 7=Desert, 8=Sky, 9=Forest) |
| 0x1    | 0x1  | Scroll Type (0=None, 1=Slow, 2=Normal, 3=Fast, 4=Custom) |
| 0x2    | 0x1  | Unknown |
| 0x3    | 0x1  | Area Orientation (0=Horizontal, 1=Vertical) |
| 0x4    | 0x1  | End Liquid Height |
| 0x5    | 0x1  | Liquid Mode (0=Static, 1=Rising/Falling Only, 2=Rising and Falling) |
| 0x6    | 0x1  | Liquid Speed (1=x1, 2=x2, 3=x3) |
| 0x7    | 0x1  | Start Liquid Height |
| 0x8    | 0x4  | Right Boundary |
| 0xC    | 0x4  | Top Boundary |
| 0x10   | 0x4  | Left Boundary |
| 0x14   | 0x4  | Bottom Boundary |
| 0x18   | 0x4  | Time (0=Day, 2=Night) |
| 0x1C   | 0x4  | Object Count |
| 0x20   | 0x4  | Sound Effect Count |
| 0x24   | 0x4  | Snake Block Count |
| 0x28   | 0x4  | Clear Pipe Count |
| 0x2C   | 0x4  | Piranha Creeper Count |
| 0x30   | 0x4  | Expanding Block Count |
| 0x34   | 0x4  | Track Block Count |
| 0x38   | 0x4  | Padding |
| 0x3C   | 0x4  | Tile Count |
| 0x40   | 0x4  | Track Count |
| 0x44   | 0x4  | Icicle Count |

### Object Data

Starts at 0x248, with a size of 0x20 * the amount of objects.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x4  | X Position |
| 0x4    | 0x4  | Y Position |
| 0x8    | 0x2  | Padding |
| 0xA    | 0x1  | Width |
| 0xB    | 0x1  | Height |
| 0xC    | 0x4  | Object Flags |
| 0x10   | 0x4  | Child Object Flags |
| 0x14   | 0x4  | Extended Data |
| 0x18   | 0x2  | Object Type |
| 0x1A   | 0x2  | Child Object Type |
| 0x1C   | 0x2  | Link ID |
| 0x1E   | 0x2  | Sound Effect ID |

### Sound Effect Data

Starts at 0x14548, with a size of 0x4 * the amount of sound effects.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x1  | Sound Effect ID |
| 0x1    | 0x1  | X Position |
| 0x2    | 0x1  | Y Position |
| 0x3    | 0x1  | Padding |

#### Sound Effect IDs

| ID | Name |
|----|------|
| 0 | Shock |
| 1 | Clatter |
| 2 | Kick |
| 3 | Applause |
| 4 | Glory |
| 5 | Punch |
| 6 | Laughter |
| 7 | Baby |
| 8 | Ding Dong |
| 9 | Boss Music |
| 10 | Heartbeat |
| 11 | Scream |
| 12 | Drama! |
| 13 | Jump |
| 14 | Cheer |
| 15 | Doom |
| 16 | Fireworks |
| 17 | Honk Honk |
| 18 | Bzzt! |
| 19 | Bonus Music |
| 20 | Silence |
| 23 | Party Popper |
| 24 | Booo! |
| 25 | Guffaw |
| 26 | Near Miss |
| 29 | Oink |
| 30 | Kuh-thunk! |
| 31 | Beep! |
| 32 | Ninja Attack! |
| 35 | Zap! |
| 36 | Flash |
| 37 | Yeah! |
| 38 | Aww... |
| 41 | Audience |
| 42 | Scatting |
| 43 | Spark |
| 44 | Traditional |
| 45 | Electric Guitar |
| 46 | Twisty Turny |
| 47 | Woozy |
| 48 | Final Boss |
| 49 | Peaceful |
| 50 | Horror |
| 51 | Super Mario Galaxy |
| 52 | Super Mario 64 |
| 53 | Super Mario Sunshine |
| 54 | Super Mario Kart |

### Tile Data

Starts at 0x247A4, with a size of 0x4 * the amount of tiles.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x1  | X Position |
| 0x1    | 0x1  | Y Position |
| 0x2    | 0x1  | Tile ID |
| 0x3    | 0x1  | Background Object ID (4=1x1, 8=1x2, 12=1x3, 16=3x1) |

### Track Data

Starts at 0x28824, with a size of 0xC * the amount of tracks.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x2  | Padding |
| 0x2    | 0x1  | Flags (1=Has Object) |
| 0x3    | 0x1  | X Position |
| 0x4    | 0x1  | Y Position |
| 0x5    | 0x1  | Type (0=Left/Right, 1=Up/Down, 8=3rd, 9=1st, 12=4th, 13=2nd) |
| 0x6    | 0x2  | Index |
| 0x8    | 0x2  | Unknown (Changes depending on the size of the track) |
| 0xA    | 0x2  | Unknown (Always `04 01` if connected to a track, otherwise changes depending on the size of the track) |

### Icicle Data

Starts at 0x2CC74, with a size of 0x4 * the amount of icicles.

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x1  | X Position |
| 0x1    | 0x1  | Y Position |
| 0x2    | 0x1  | Type (0=Regular Icicle, 1=Hard Icicle) |
| 0x3    | 0x1  | Padding |
