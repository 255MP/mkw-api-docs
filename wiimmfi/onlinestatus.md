# Wiimmfi: Game Statistics/Online Status

Game statistic/online status information can be viewed at [https://wiimmfi.de/stats/game/mariokartwii](https://wiimmfi.de/stats/game/mariokartwii)

A machine-readable format can be viewed at [https://wiimmfi.de/stats/game/mariokartwii/text](https://wiimmfi.de/stats/game/mariokartwii/text)

## ol_stat

| bit | hex mask | char | description                                             |
| --- | -------- | ---- | ------------------------------------------------------- |
| 0   | 0x0001   | o    | Player is online                                        |
| 1   | 0x0002   | P    | Private room                                            |
| 2   | 0x0004   | G    | Global race or battle (either continental or worldwide) |
| 3   | 0x0008   | c    | Continental (regional) race or battle                   |
| 4   | 0x0010   | w    | Worldwide race or battle                                |
| 5   | 0x0020   | A    | Active race or battle                                   |
| 6   | 0x0040   | R    | Playing or waiting for a race                           |
| 7   | 0x0080   | B    | Playing or waiting for a battle                         |
| 8   | 0x0100   | h    | Player is the host                                      |
| 9   | 0x0200   | g    | Player is a guest                                       |
| 10  | 0x0400   | v    | Player is a viewer                                      |
| 12  | 0x1000   | S    | Player is searching for a global room                   |
| 13  | 0x2000   | C    | Player is connecting to a room                          |
