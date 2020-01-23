## Course Structure
This is the structure of the course file, which has a size of 0x5BFC0.

| Offset  | Size    | Description             |
|---------|---------|-------------------------|
| 0x0     | 0x200   | Course Header           |
| 0x200   | 0x2DEE0 | Course Data (Main Area) |
| 0x2E0E0 | 0x2DEE0 | Course Data (Sub Area)  |

## Course Header
Starts at 0x0, with a size of 0x200.

| Offset | Size | Description                                                                                                                                                                                                                                                                           |
|--------|------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x1  | Start Y Position                                                                                                                                                                                                                                                                      |
| 0x1    | 0x1  | Goal Y Position                                                                                                                                                                                                                                                                       |
| 0x2    | 0x2  | Goal X Position                                                                                                                                                                                                                                                                       |
| 0x4    | 0x2  | Time Limit                                                                                                                                                                                                                                                                            |
| 0x6    | 0x2  | Clear Condition Amount                                                                                                                                                                                                                                                                |
| 0x8    | 0x2  | Last Saved Year                                                                                                                                                                                                                                                                       |
| 0xA    | 0x1  | Last Saved Month                                                                                                                                                                                                                                                                      |
| 0xB    | 0x1  | Last Saved Day                                                                                                                                                                                                                                                                        |
| 0xC    | 0x1  | Last Saved Hour                                                                                                                                                                                                                                                                       |
| 0xD    | 0x1  | Last Saved Minute                                                                                                                                                                                                                                                                     |
| 0xE    | 0x1  | Custom Autoscroll Speed (0=x1, 1=x2, 2=x3)                                                                                                                                                                                                                                            |
| 0xF    | 0x1  | Clear Condition Category (1=Parts, 2=Status, 3=Actions)                                                                                                                                                                                                                               |
| 0x10   | 0x4  | Clear Condition CRC32                                                                                                                                                                                                                                                                 |
| 0x14   | 0x4  | Course Game Version Built (bit0=1.0.0, bit1=1.0.1. Both set if the course was created in 1.0.0, and then edited in 1.0.1)                                                                                                                                                             |
| 0x18   | 0x4  | Management Flags (bit0=Needs to be set, but isn't for quest_105 and quest_115. bit1=Has passed clear check, bit4=Cant upload course, bit5=Has clear condition amount, bit6=Has chosen sub area orientation. bit2 and bit7 are unseen, bit3 is used only for Lesson and Quest courses) |
| 0x1C   | 0x4  | Number of Clear Check Tries                                                                                                                                                                                                                                                           |
| 0x20   | 0x4  | Clear Check Time                                                                                                                                                                                                                                                                      |
| 0x24   | 0x4  | Creation ID                                                                                                                                                                                                                                                                           |
| 0x28   | 0x8  | Upload ID                                                                                                                                                                                                                                                                             |
| 0x30   | 0x4  | Course Flags (1=Completed, 2+=Unknown)                                                                                                                                                                                                                                                |
| 0x34   | 0xBC | Padding                                                                                                                                                                                                                                                                               |
| 0xF0   | 0x1  | Unknown, usually FF                                                                                                                                                                                                                                                                   |
| 0xF1   | 0x3  | Game Style (M1, M3, MW, WU, 3W)                                                                                                                                                                                                                                                       |
| 0xF4   | 0x42 | Course Name, 32 characters, null-terminated                                                                                                                                                                                                                                           |
| 0x136  | 0xCA | Course Description, 75 characters with space for 100, null-terminated                                                                                                                                                                                                                 |

## Course Data
Each entry has a size of 0x48.

| Offset  | Size        | Description                                                                                                               |
|---------|-------------|---------------------------------------------------------------------------------------------------------------------------|
| 0x0     | 0x1         | Area Theme (0=Ground, 1=Underground, 2=Castle, 3=Airship, 4=Underwater, 5=Ghost House, 6=Snow, 7=Desert, 8=Sky, 9=Forest) |
| 0x1     | 0x1         | Autoscroll Type (0=None, 1=Slow, 2=Normal, 3=Fast, 4=Custom)                                                              |
| 0x2     | 0x1         | Screen Boundary Flags (0=Built Above Line, 1=Only Built Under Line)                                                       |
| 0x3     | 0x1         | Area Orientation (0=Horizontal, 1=Vertical)                                                                               |
| 0x4     | 0x1         | End Liquid Height                                                                                                         |
| 0x5     | 0x1         | Liquid Mode (0=Static, 1=Rising/Falling Only, 2=Rising and Falling)                                                       |
| 0x6     | 0x1         | Liquid Speed (1=x1, 2=x2, 3=x3)                                                                                           |
| 0x7     | 0x1         | Start Liquid Height                                                                                                       |
| 0x8     | 0x4         | Right Boundary                                                                                                            |
| 0xC     | 0x4         | Top Boundary                                                                                                              |
| 0x10    | 0x4         | Left Boundary                                                                                                             |
| 0x14    | 0x4         | Bottom Boundary                                                                                                           |
| 0x18    | 0x4         | Area Flags (bit0=Related to Screen Lock?, bit1=Night Time)                                                                |
| 0x1C    | 0x4         | Object Count                                                                                                              |
| 0x20    | 0x4         | Sound Effect Count                                                                                                        |
| 0x24    | 0x4         | Snake Block Count                                                                                                         |
| 0x28    | 0x4         | Clear Pipe Count                                                                                                          |
| 0x2C    | 0x4         | Piranha Creeper Count                                                                                                     |
| 0x30    | 0x4         | ! Block Count                                                                                                             |
| 0x34    | 0x4         | Track Block Count                                                                                                         |
| 0x38    | 0x4         | Padding                                                                                                                   |
| 0x3C    | 0x4         | Tile Count                                                                                                                |
| 0x40    | 0x4         | Track Count                                                                                                               |
| 0x44    | 0x4         | Icicle Count                                                                                                              |
| 0x48    | 0x20 * 2600 | Object Data                                                                                                               |
| 0x14584 | 0x4 * 300   | Sound Effect Data                                                                                                         |
| 0x149F8 | 0x3C4 * 5   | Snake Block Data                                                                                                          |
| 0x15CCC | 0x124 * 200 | Clear Pipe Data                                                                                                           |
| 0x240EC | 0x54 * 10   | Piranha Creeper Data                                                                                                      |
| 0x24434 | 0x2C * 10   | ! Block Data                                                                                                              |
| 0x245EC | 0x2C * 10   | Track Block Data                                                                                                          |
| 0x247A4 | 0x4 * 4000  | Tile Data                                                                                                                 |
| 0x28624 | 0xC * 1500  | Track Data                                                                                                                |
| 0x2CC74 | 0x4 * 300   | Icicle Data                                                                                                               |
| 0x2D124 | 0xDBC       | Padding                                                                                                                   |

### Object Data
Each entry has a size of 0x20 * the amount of objects.

| Offset | Size | Description        |
|--------|------|--------------------|
| 0x0    | 0x4  | X Position         |
| 0x4    | 0x4  | Y Position         |
| 0x8    | 0x2  | Padding            |
| 0xA    | 0x1  | Width              |
| 0xB    | 0x1  | Height             |
| 0xC    | 0x4  | Object Flags       |
| 0x10   | 0x4  | Child Object Flags |
| 0x14   | 0x4  | Extended Data      |
| 0x18   | 0x2  | Object Type        |
| 0x1A   | 0x2  | Child Object Type  |
| 0x1C   | 0x2  | Link ID            |
| 0x1E   | 0x2  | Sound Effect ID    |

### Sound Effect Data
Each entry has a size of 0x4 * the amount of sound effects.

| Offset | Size | Description     |
|--------|------|-----------------|
| 0x0    | 0x1  | Sound Effect ID |
| 0x1    | 0x1  | X Position      |
| 0x2    | 0x1  | Y Position      |
| 0x3    | 0x1  | Padding         |

#### Sound Effect IDs
| ID | Name                 |
|----|----------------------|
| 0  | Shock                |
| 1  | Clatter              |
| 2  | Kick                 |
| 3  | Applause             |
| 4  | Glory                |
| 5  | Punch                |
| 6  | Laughter             |
| 7  | Baby                 |
| 8  | Ding Dong            |
| 9  | Boss Music           |
| 10 | Heartbeat            |
| 11 | Scream               |
| 12 | Drama!               |
| 13 | Jump                 |
| 14 | Cheer                |
| 15 | Doom                 |
| 16 | Fireworks            |
| 17 | Honk Honk            |
| 18 | Bzzt!                |
| 19 | Bonus Music          |
| 20 | Silence              |
| 23 | Party Popper         |
| 24 | Booo!                |
| 25 | Guffaw               |
| 26 | Near Miss            |
| 29 | Oink                 |
| 30 | Kuh-thunk!           |
| 31 | Beep!                |
| 32 | Ninja Attack!        |
| 35 | Zap!                 |
| 36 | Flash                |
| 37 | Yeah!                |
| 38 | Aww...               |
| 41 | Audience             |
| 42 | Scatting             |
| 43 | Spark                |
| 44 | Traditional          |
| 45 | Electric Guitar      |
| 46 | Twisty Turny         |
| 47 | Woozy                |
| 48 | Final Boss           |
| 49 | Peaceful             |
| 50 | Horror               |
| 51 | Super Mario Galaxy   |
| 52 | Super Mario 64       |
| 53 | Super Mario Sunshine |
| 54 | Super Mario Kart     |

### Snake Block Data
Each entry has a size of 0x3C4 * the amount of snake blocks.

| Offset | Size      | Description        |
|--------|-----------|--------------------|
| 0x0    | 0x1       | Link ID            |
| 0x1    | 0x2       | Node Count         |
| 0x2    | 0x1       | Unknown (Always 1) |
| 0x3    | 0x1       | Padding            |
| 0x4    | 0x8 * 120 | Snake Block Nodes  |

#### Snake Block Nodes
Each entry  has a size of 0x8 * the amount of snake block nodes.

| Offset | Size | Description                                                                                                                                                                                                                             |
|--------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x2  | Index                                                                                                                                                                                                                                   |
| 0x2    | 0x2  | Direction (1=Left, 2=Right, 3=Down, 4=Up, 5=Left to Down, 6=Down to Left, 7=Left to Up, 8=Up to Left, 9=Right to Down, 10=Down to Right, 11=Right to Up, 12=Up to Right, 13=Right to End, 14=Left to End, 15=Up to End, 16=Down to End) |
| 0x4    | 0x2  | Unknown (Always 100)                                                                                                                                                                                                                    |
| 0x6    | 0x2  | Padding                                                                                                                                                                                                                                 |

### Clear Pipe Data
Each entry has a size of 0x4 * the amount of clear pipes.

| Offset | Size     | Description        |
|--------|----------|--------------------|
| 0x0    | 0x1      | Link ID            |
| 0x1    | 0x1      | Node Count         |
| 0x2    | 0x1      | Unknown (Always 1) |
| 0x3    | 0x1      | Padding            |
| 0x4    | 0x8 * 36 | Clear Pipe Nodes   |

#### Clear Pipe Nodes
Each entry has a size of 0x8 * the amount of clear pipe nodes.

| Offset | Size     | Description            |
|--------|----------|------------------------|
| 0x0    | 0x1      | Unknown (Direction?)   |
| 0x1    | 0x1      | Index                  |
| 0x2    | 0x1      | Unknown (Position?)    |
| 0x3    | 0x1      | Unknown (Position?)    |
| 0x4    | 0x1      | Unknown (Always 2)     |
| 0x5    | 0x1      | Unknown                |
| 0x6    | 0x1      | Unknown (Always 1)     |
| 0x7    | 0x1      | Unknown (Seen 0/1/2/3) |

### Piranha Creeper Data
Each entry has a size of 0x54 * the amount of piranha creepers.

| Offset | Size     | Description           |
|--------|----------|-----------------------|
| 0x0    | 0x1      | Unknown (Always 1)    |
| 0x1    | 0x1      | Link ID               |
| 0x2    | 0x1      | Node Count            |
| 0x3    | 0x1      | Padding               |
| 0x4    | 0x4 * 20 | Piranha Creeper Nodes |

#### Piranha Creeper Nodes
Each entry has a size of 0x4 * the amount of piranha creeper nodes.

| Offset | Size | Description                                                                                                                                                                                                                             |
|--------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x1  | Unknown (Always 1)                                                                                                                                                                                                                      |
| 0x1    | 0x1  | Direction (1=Left, 2=Right, 3=Down, 4=Up, 5=Left to Down, 6=Down to Left, 7=Left to Up, 8=Up to Left, 9=Right to Down, 10=Down to Right, 11=Right to Up, 12=Up to Right, 13=Right to End, 14=Left to End, 15=Up to End, 16=Down to End) |
| 0x2    | 0x2  | Padding                                                                                                                                                                                                                                 |

### ! Block Data
Each entry has a size of 0x2C * the amount of ! blocks.

| Offset | Size     | Description        |
|--------|----------|--------------------|
| 0x0    | 0x1      | Unknown (Always 1) |
| 0x1    | 0x1      | Link ID            |
| 0x2    | 0x1      | Node Count         |
| 0x3    | 0x1      | Padding            |
| 0x4    | 0x4 * 10 | ! Block Nodes      |

#### ! Block Nodes
Each entry has a size of 0x4 * the amount of ! block nodes.

| Offset | Size | Description                                                                                                                                                                                                                             |
|--------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x1  | Unknown (Always 1)                                                                                                                                                                                                                      |
| 0x1    | 0x1  | Direction (1=Left, 2=Right, 3=Down, 4=Up, 5=Left to Down, 6=Down to Left, 7=Left to Up, 8=Up to Left, 9=Right to Down, 10=Down to Right, 11=Right to Up, 12=Up to Right, 13=Right to End, 14=Left to End, 15=Up to End, 16=Down to End) |
| 0x2    | 0x2  | Padding                                                                                                                                                                                                                                 |

### Track Block Data
Each entry has a size of 0x2C * the amount of track blocks.‬

| Offset | Size     | Description        |
|--------|----------|--------------------|
| 0x0    | 0x1      | Unknown (Always 1) |
| 0x1    | 0x1      | Link ID            |
| 0x2    | 0x1      | Node Count         |
| 0x3    | 0x1      | Padding            |
| 0x4    | 0x4 * 10 | Track Block Nodes  |

#### Track Block Nodes
Each entry has a size of 0x4 * the amount of track block nodes.

| Offset | Size | Description                                                                                                                                                                                                                             |
|--------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x1  | Unknown (Always 1)                                                                                                                                                                                                                      |
| 0x1    | 0x1  | Direction (1=Left, 2=Right, 3=Down, 4=Up, 5=Left to Down, 6=Down to Left, 7=Left to Up, 8=Up to Left, 9=Right to Down, 10=Down to Right, 11=Right to Up, 12=Up to Right, 13=Right to End, 14=Left to End, 15=Up to End, 16=Down to End) |
| 0x2    | 0x2  | Padding                                                                                                                                                                                                                                 |

### Tile Data
Each entry has a size of 0x4 * the amount of tiles.

| Offset | Size | Description                                         |
|--------|------|-----------------------------------------------------|
| 0x0    | 0x1  | X Position                                          |
| 0x1    | 0x1  | Y Position                                          |
| 0x2    | 0x1  | Tile ID                                             |
| 0x3    | 0x1  | Background Object ID (4=1x1, 8=1x2, 12=1x3, 16=3x1) |

### Track Data
Each entry has a size of 0xC * the amount of tracks.

| Offset | Size | Description                                                                                                                                                                                                                                                                                                                                        |
|--------|------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x2  | Padding                                                                                                                                                                                                                                                                                                                                            |
| 0x2    | 0x1  | Flags (1=Has Object)                                                                                                                                                                                                                                                                                                                               |
| 0x3    | 0x1  | X Position                                                                                                                                                                                                                                                                                                                                         |
| 0x4    | 0x1  | Y Position                                                                                                                                                                                                                                                                                                                                         |
| 0x5    | 0x1  | Type (0=Horizontal, 1=Vertical, 2=Descending Diagonal, 3=Ascending Diagonal, 4=Bottom Left Curve, 5=Top Right Curve, 6=Top Left Curve, 7=Bottom Right Curve, 8=Horizontal 3rd Type, 9=Horizontal 1st Type, 10=Vertical 3rd Type, 11=Vertical 1st Type, 12=Horizontal 4th Type, 13=Horizontal 2nd Type, 14=Vertical 4th Type, 15=Vertical 2nd Type) |
| 0x6    | 0x2  | Index                                                                                                                                                                                                                                                                                                                                              |
| 0x8    | 0x2  | Unknown (Changes depending on the size of the track, usually + 10 if the track is not looped)                                                                                                                                                                                                                                                      |
| 0xA    | 0x2  | Unknown (Always `04 01` if connected to a track, otherwise changes depending on the size of the track, usually + 10 if the track is not looped)                                                                                                                                                                                                    |

### Icicle Data
Each entry has a size of 0x4 * the amount of icicles.

| Offset | Size | Description               |
|--------|------|---------------------------|
| 0x0    | 0x1  | X Position                |
| 0x1    | 0x1  | Y Position                |
| 0x2    | 0x1  | Type (0=Falling, 1=Solid) |
| 0x3    | 0x1  | Padding                   |
