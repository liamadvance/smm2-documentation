## Course Structure

This is the structure of the course file, which has a size of 0x5BFC0.

| Offset  | Size    | Description             |
|---------|---------|-------------------------|
| 0x0     | 0x200   | Course Header           |
| 0x200   | 0x2DEE0 | Course Area (Main Area) |
| 0x2E0E0 | 0x2DEE0 | Course Area (Sub Area)  |

## Course Header

| Offset | Size | Description                                                                                                                               |
|--------|------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x1  | Start Y Position                                                                                                                          |
| 0x1    | 0x1  | Goal Y Position                                                                                                                           |
| 0x2    | 0x2  | Goal X Position                                                                                                                           |
| 0x4    | 0x2  | Timer                                                                                                                                     |
| 0x6    | 0x2  | Clear Condition Amount                                                                                                                    |
| 0x8    | 0x2  | Last Saved Year                                                                                                                           |
| 0xA    | 0x1  | Last Saved Month                                                                                                                          |
| 0xB    | 0x1  | Last Saved Day                                                                                                                            |
| 0xC    | 0x1  | Last Saved Hour                                                                                                                           |
| 0xD    | 0x1  | Last Saved Minute                                                                                                                         |
| 0xE    | 0x1  | Custom Autoscroll Speed                                                                                                                   |
| 0xF    | 0x1  | Clear Condition Category                                                                                                                  |
| 0x10   | 0x4  | Clear Condition CRC32                                                                                                                     |
| 0x14   | 0x4  | [Game Version](#Game%20Version) create and edit bits. Multiple bits are set, if the course was created and/or edited in multiple versions |
| 0x18   | 0x4  | [Management Flags](#Management%20Flags)                                                                                                   |
| 0x1C   | 0x4  | Clear Check Attempts                                                                                                                      |
| 0x20   | 0x4  | Clear Check Time                                                                                                                          |
| 0x24   | 0x4  | Creation ID                                                                                                                               |
| 0x28   | 0x8  | Upload ID                                                                                                                                 |
| 0x30   | 0x4  | [Clear Check Game Version](#Game%20Version)                                                                                               |
| 0x34   | 0xBC | Reserved                                                                                                                                  |
| 0xF0   | 0x1  | Unknown (Usually 0xFF)                                                                                                                    |
| 0xF1   | 0x3  | Game Style (null-terminated)                                                                                                              |
| 0xF4   | 0x42 | Name (32 characters, null-terminated)                                                                                                     |
| 0x136  | 0xCA | Description (75 characters with space for 100, null-terminated)                                                                           |

### Custom Autoscroll Speed

| Value | Description |
|-------|-------------|
| 0     | x1          |
| 1     | x2          |
| 2     | x3          |

### Clear Condition Category

| Value | Description |
|-------|-------------|
| 0     | None        |
| 1     | Parts       |
| 2     | Status      |
| 3     | Actions     |

### Clear Condition CRC32

| Value      | Description                           |
|------------|---------------------------------------|
| 0x1664515A | Reach the goal without taking damage. |
| 0x4C8772A3 | Reach the goal on a Lakitu's Cloud.   |

### Game Version

| Value | Description |
|-------|-------------|
| 0     | 1.0.0       |
| 1     | 1.0.1       |
| 2     | 1.1.0       |
| 3     | 2.0.0       |
| 4     | 3.0.0       |
| 5     | 3.0.1       |

### Management Flags

| Bit | Description                                            |
|-----|--------------------------------------------------------|
| 0   | Needs to be set, but isn't for quest_105 and quest_115 |
| 1   | Has passed clear check                                 |
| 2   | Unknown                                                |
| 3   | Used only for Lesson and Quest courses                 |
| 4   | Can't upload course                                    |
| 5   | Has clear condition amount                             |
| 6   | Has chosen sub area orientation                        |
| 7   | Unknown                                                |

If bit0 is not set in a course, then opening the Coursebot will show an error indicating that the course is corrupted.

### Game Style

| Value | Description             |
|-------|-------------------------|
| "M1"  | Super Mario Bros.       |
| "M3"  | Super Mario Bros. 3     |
| "MW"  | Super Mario World       |
| "WU"  | New Super Mario Bros. U |
| "3W"  | Super Mario 3D World    |

## Course Area

| Offset  | Size                  | Description           |
|---------|-----------------------|-----------------------|
| 0x0     | 0x48                  | Course Area Header    |
| 0x48    | 0x14500 (0x20 * 2600) | Object Data           |
| 0x14584 | 0x4B0 (0x4 * 300)     | Sound Effect Data     |
| 0x149F8 | 0x12D4 (0x3C4 * 5)    | Snake Block Data      |
| 0x15CCC | 0xE420 (0x124 * 200)  | Clear Pipe Data       |
| 0x240EC | 0x348 (0x54 * 10)     | Piranha Creeper Data  |
| 0x24434 | 0x1B8 (0x2C * 10)     | ! Block Data          |
| 0x245EC | 0x1B8 (0x2C * 10)     | Track Block Data      |
| 0x247A4 | 0x3E80 (0x4 * 4000)   | Ground Data           |
| 0x28624 | 0x4650 (0xC * 1500)   | Track Data            |
| 0x2CC74 | 0x4B0 (0x4 * 300)     | Icicle Data           |
| 0x2D124 | 0xDBC                 | Reserved              |

### Course Area Header

| Offset  | Size                  | Description           |
|---------|-----------------------|-----------------------|
| 0x0     | 0x1                   | Theme                 |
| 0x1     | 0x1                   | Autoscroll Type       |
| 0x2     | 0x1                   | Boundary Flags        |
| 0x3     | 0x1                   | Orientation           |
| 0x4     | 0x1                   | End Liquid Height     |
| 0x5     | 0x1                   | Liquid Mode           |
| 0x6     | 0x1                   | Liquid Speed          |
| 0x7     | 0x1                   | Start Liquid Height   |
| 0x8     | 0x4                   | Right Boundary        |
| 0xC     | 0x4                   | Top Boundary          |
| 0x10    | 0x4                   | Left Boundary         |
| 0x14    | 0x4                   | Bottom Boundary       |
| 0x18    | 0x4                   | Area Flags            |
| 0x1C    | 0x4                   | Object Count          |
| 0x20    | 0x4                   | Sound Effect Count    |
| 0x24    | 0x4                   | Snake Block Count     |
| 0x28    | 0x4                   | Clear Pipe Count      |
| 0x2C    | 0x4                   | Piranha Creeper Count |
| 0x30    | 0x4                   | ! Block Count         |
| 0x34    | 0x4                   | Track Block Count     |
| 0x38    | 0x4                   | Reserved              |
| 0x3C    | 0x4                   | Ground Count          |
| 0x40    | 0x4                   | Track Count           |
| 0x44    | 0x4                   | Icicle Count          |

#### Theme

| Value | Description |
|-------|-------------|
| 0     | Ground      |
| 1     | Underground |
| 2     | Castle      |
| 3     | Airship     |
| 4     | Underwater  |
| 5     | Ghost House |
| 6     | Snow        |
| 7     | Desert      |
| 8     | Sky         |
| 9     | Forest      |

#### Autoscroll Type

| Value | Description |
|-------|-------------|
| 0     | None        |
| 1     | Slow        |
| 2     | Normal      |
| 3     | Fast        |
| 4     | Custom      |

#### Boundary Flags

| Value | Description      |
|-------|------------------|
| 0     | Built Above Line |
| 1     | Built Under Line |

#### Orientation

| Value | Description |
|-------|-------------|
| 0     | Horizontal  |
| 1     | Vertical    |

#### Liquid Mode

| Value | Description        |
|-------|--------------------|
| 0     | Static             |
| 1     | Rising or Falling  |
| 2     | Rising and Falling |

#### Liquid Speed

| Value | Description |
|-------|-------------|
| 0     | None        |
| 1     | x1          |
| 2     | x2          |
| 3     | x3          |

#### Area Flags

| Bit   | Description                       |
|-------|-----------------------------------|
| 0     | Unknown (Related to Screen Lock?) |
| 1     | Night Time                        |

### Object Data

| Offset | Size | Description        |
|--------|------|--------------------|
| 0x0    | 0x4  | X Position         |
| 0x4    | 0x4  | Y Position         |
| 0x8    | 0x2  | Reserved           |
| 0xA    | 0x1  | Width              |
| 0xB    | 0x1  | Height             |
| 0xC    | 0x4  | Flags              |
| 0x10   | 0x4  | Child Flags        |
| 0x14   | 0x4  | Extended Data      |
| 0x18   | 0x2  | ID                 |
| 0x1A   | 0x2  | Child ID           |
| 0x1C   | 0x2  | Link ID            |
| 0x1E   | 0x2  | Sound Effect ID    |

### Sound Effect Data

| Offset | Size | Description     |
|--------|------|-----------------|
| 0x0    | 0x1  | ID              |
| 0x1    | 0x1  | X Position      |
| 0x2    | 0x1  | Y Position      |
| 0x3    | 0x1  | Reserved        |

#### Sound Effect IDs

| ID | Name                 | Category   |
|----|----------------------|------------|
| 0  | Shock                | Feelings   |
| 1  | Clatter              | Stingers   |
| 2  | Kick                 | Stingers   |
| 3  | Applause             | Feelings   |
| 4  | Glory                | Reactions  |
| 5  | Punch                | Stingers   |
| 6  | Laughter             | Feelings   |
| 7  | Baby                 | Feelings   |
| 8  | Ding Dong            | Reactions  |
| 9  | Boss Music           | Music      |
| 10 | Heartbeat            | Music      |
| 11 | Scream               | Feelings   |
| 12 | Drama!               | Stingers   |
| 13 | Jump                 | Stingers   |
| 14 | Cheer                | Feelings   |
| 15 | Doom                 | Reactions  |
| 16 | Fireworks            | Animations |
| 17 | Honk Honk            | Stingers   |
| 18 | Bzzt!                | Reactions  |
| 19 | Bonus Music          | Music      |
| 20 | Silence              | Music      |
| 21 | Unknown              | Unknown    |
| 22 | Unknown              | Unknown    |
| 23 | Party Popper         | Feelings   |
| 24 | Booo!                | Feelings   |
| 25 | Guffaw               | Feelings   |
| 26 | Near Miss            | Feelings   |
| 27 | Unknown              | Unknown    |
| 28 | Unknown              | Unknown    |
| 29 | Oink                 | Stingers   |
| 30 | Kuh-thunk!           | Stingers   |
| 31 | Beep!                | Stingers   |
| 32 | Ninja Attack         | Stingers   |
| 33 | Unknown              | Unknown    |
| 34 | Unknown              | Unknown    |
| 35 | Zap!                 | Stingers   |
| 36 | Flash                | Animations |
| 37 | Yeah!                | Reactions  |
| 38 | Aww...               | Reactions  |
| 39 | Unknown              | Unknown    |
| 40 | Unknown              | Unknown    |
| 41 | Audience             | Animations |
| 42 | Scatting             | Animations |
| 43 | Spark                | Animations |
| 44 | Traditional          | Animations |
| 45 | Electric Guitar      | Animations |
| 46 | Twisty Turny         | Animations |
| 47 | Woozy                | Animations |
| 48 | Final Boss           | Music      |
| 49 | Peaceful             | Music      |
| 50 | Horror               | Music      |
| 51 | Super Mario Galaxy   | Music      |
| 52 | Super Mario 64       | Music      |
| 53 | Super Mario Sunshine | Music      |
| 54 | Super Mario Kart     | Music      |
| 55 | Unknown              | Unknown    |

ID 21 appears to be the same as the Scatting (ID 42) sound effect, but without the visual effect.

### Snake Block Data

| Offset | Size              | Description          |
|--------|-------------------|----------------------|
| 0x0    | 0x1               | Index                |
| 0x1    | 0x2               | Node Count           |
| 0x2    | 0x1               | Unknown (Always `1`) |
| 0x3    | 0x1               | Reserved             |
| 0x4    | 0x3C0 (0x8 * 120) | Snake Block Nodes    |

#### Snake Block Node

| Offset | Size | Description              |
|--------|------|--------------------------|
| 0x0    | 0x2  | Index                    |
| 0x2    | 0x2  | Direction                |
| 0x4    | 0x2  | Unknown (Always `0x100`) |
| 0x6    | 0x2  | Reserved                 |

##### Direction

| Value | Description   |
|-------|---------------|
| 1     | Left          |
| 2     | Right         |
| 3     | Down          |
| 4     | Up            |
| 5     | Left to Down  |
| 6     | Down to Left  |
| 7     | Left to Up    |
| 8     | Up to Left    |
| 9     | Right to Down |
| 10    | Down to Right |
| 11    | Right to Up   |
| 12    | Up to Right   |
| 13    | Right to End  |
| 14    | Left to End   |
| 15    | Up to End     |
| 16    | Down to End   |

### Clear Pipe Data

| Offset | Size             | Description          |
|--------|------------------|----------------------|
| 0x0    | 0x1              | Index                |
| 0x1    | 0x1              | Node Count           |
| 0x2    | 0x1              | Unknown (Always `1`) |
| 0x3    | 0x1              | Reserved             |
| 0x4    | 0x120 (0x8 * 36) | Clear Pipe Nodes     |

#### Clear Pipe Node

| Offset | Size | Description          |
|--------|------|----------------------|
| 0x0    | 0x1  | Type                 |
| 0x1    | 0x1  | Index                |
| 0x2    | 0x1  | X Position           |
| 0x3    | 0x1  | Y Position           |
| 0x4    | 0x1  | Width                |
| 0x5    | 0x1  | Height               |
| 0x6    | 0x1  | Unknown (Always `1`) |
| 0x7    | 0x1  | Direction            |

##### Type

| Value | Description                  |
|-------|------------------------------|
| 0     | Closed on opposite direction |
| 1     | Closed on direction          |
| 2     | Open                         |
| 3+    | Unknown                      |

Values 0 and 1 will cause a part of the clear pipe to become "closed", as seen in the below image.

![image](https://user-images.githubusercontent.com/47696410/129957779-782842a6-62ec-4ea2-9053-5af2392ca070.png)

With a basic 2x3 right direction clear pipe, setting the Type field to 3 will cause the course to corrupt.

##### Direction

| Value | Description |
|-------|-------------|
| 0     | Right       |
| 1     | Left        |
| 2     | Up          |
| 3     | Down        |

### Piranha Creeper Data

| Offset | Size            | Description             |
|--------|-----------------|-------------------------|
| 0x0    | 0x1             | Unknown (Always `1`)    |
| 0x1    | 0x1             | Index                   |
| 0x2    | 0x1             | Node Count              |
| 0x3    | 0x1             | Reserved                |
| 0x4    | 0x50 (0x4 * 20) | Piranha Creeper Nodes   |

#### Piranha Creeper Node

| Offset | Size | Description        |
|--------|------|--------------------|
| 0x0    | 0x1  | Unknown (Always 1) |
| 0x1    | 0x1  | Direction          |
| 0x2    | 0x2  | Reserved           |

##### Direction

| Value | Description   |
|-------|---------------|
| 1     | Left          |
| 2     | Right         |
| 3     | Down          |
| 4     | Up            |
| 5     | Left to Down  |
| 6     | Down to Left  |
| 7     | Left to Up    |
| 8     | Up to Left    |
| 9     | Right to Down |
| 10    | Down to Right |
| 11    | Right to Up   |
| 12    | Up to Right   |
| 13    | Right to End  |
| 14    | Left to End   |
| 15    | Up to End     |
| 16    | Down to End   |

### ! Block Data

| Offset | Size            | Description          |
|--------|-----------------|----------------------|
| 0x0    | 0x1             | Unknown (Always `1`) |
| 0x1    | 0x1             | Index                |
| 0x2    | 0x1             | Node Count           |
| 0x3    | 0x1             | Reserved             |
| 0x4    | 0x28 (0x4 * 10) | ! Block Nodes        |

#### ! Block Node

| Offset | Size | Description          |
|--------|------|----------------------|
| 0x0    | 0x1  | Unknown (Always `1`) |
| 0x1    | 0x1  | Direction            |
| 0x2    | 0x2  | Reserved             |

##### Direction

| Value | Description   |
|-------|---------------|
| 1     | Left          |
| 2     | Right         |
| 3     | Down          |
| 4     | Up            |
| 5     | Left to Down  |
| 6     | Down to Left  |
| 7     | Left to Up    |
| 8     | Up to Left    |
| 9     | Right to Down |
| 10    | Down to Right |
| 11    | Right to Up   |
| 12    | Up to Right   |
| 13    | Right to End  |
| 14    | Left to End   |
| 15    | Up to End     |
| 16    | Down to End   |

### Track Block Data

| Offset | Size            | Description          |
|--------|-----------------|----------------------|
| 0x0    | 0x1             | Unknown (Always `1`) |
| 0x1    | 0x1             | Index                |
| 0x2    | 0x1             | Node Count           |
| 0x3    | 0x1             | Reserved             |
| 0x4    | 0x28 (0x4 * 10) | Track Block Nodes    |

#### Track Block Node

| Offset | Size | Description          |
|--------|------|----------------------|
| 0x0    | 0x1  | Unknown (Always `1`) |
| 0x1    | 0x1  | Direction            |
| 0x2    | 0x2  | Reserved             |

##### Direction

| Value | Description   |
|-------|---------------|
| 1     | Left          |
| 2     | Right         |
| 3     | Down          |
| 4     | Up            |
| 5     | Left to Down  |
| 6     | Down to Left  |
| 7     | Left to Up    |
| 8     | Up to Left    |
| 9     | Right to Down |
| 10    | Down to Right |
| 11    | Right to Up   |
| 12    | Up to Right   |
| 13    | Right to End  |
| 14    | Left to End   |
| 15    | Up to End     |
| 16    | Down to End   |

### Ground Data

| Offset | Size | Description          |
|--------|------|----------------------|
| 0x0    | 0x1  | X Position           |
| 0x1    | 0x1  | Y Position           |
| 0x2    | 0x1  | Tile ID              |
| 0x3    | 0x1  | Background Object ID |

#### Background Object ID

| Value | Description |
|-------|-------------|
| 0     | None        |
| 4     | 1x1         |
| 8     | 1x2         |
| 12    | 1x3         |
| 16    | 3x1         |

### Track Data

| Offset | Size | Description                                                                                                                                     |
|--------|------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x0    | 0x2  | Unknown                                                                                                                                         |
| 0x2    | 0x1  | Flags                                                                                                                                           |
| 0x3    | 0x1  | X Position                                                                                                                                      |
| 0x4    | 0x1  | Y Position                                                                                                                                      |
| 0x5    | 0x1  | Type                                                                                                                                            |
| 0x6    | 0x2  | Link ID                                                                                                                                         |
| 0x8    | 0x2  | Unknown (Changes depending on the size of the track, usually + 10 if the track is not looped)                                                   |
| 0xA    | 0x2  | Unknown (Always `04 01` if connected to a track, otherwise changes depending on the size of the track, usually + 10 if the track is not looped) |

#### Flags

| Value | Description |
|-------|-------------|
| 1     | Has Object  |

#### Type

| Value | Description         |
|-------|---------------------|
| 0     | Horizontal          |
| 1     | Vertical            |
| 2     | Descending Diagonal |
| 3     | Ascending Diagonal  |
| 4     | Bottom Left Curve   |
| 5     | Top Right Curve     |
| 6     | Top Left Curve      |
| 7     | Bottom Right Curve  |
| 8     | Horizontal 3        |
| 9     | Horizontal 1        |
| 10    | Vertical 3          |
| 11    | Vertical 1          |
| 12    | Horizontal 4        |
| 13    | Horizontal 2        |
| 14    | Vertical 4          |
| 15    | Vertical 5          |

### Icicle Data

| Offset | Size | Description |
|--------|------|-------------|
| 0x0    | 0x1  | X Position  |
| 0x1    | 0x1  | Y Position  |
| 0x2    | 0x1  | Type        |
| 0x3    | 0x1  | Reserved    |

#### Type

| Value | Description |
|-------|-------------|
| 0     | Falling     |
| 1     | Solid       |
