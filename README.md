# A-DIY-Thermometer
Have you ever thought that it would a sigificantly better idea to build your own thermometer rather than going to the drug store and spending the five dollars to buy one? Me neither. However, when you need a temperature reading for a control system, you have to learn how to build your own, so let's get started off with the basics then.

## Overview of Hardware Functionality
```mermaid
flowchart TB
    subgraph HW["Physical Hardware"]
        MCU["Microcontroller"]
        TS["Temperature Sensor"]
        LD["LED Display"]
        P["Power System"]
    end

    subgraph FW["Firmware"]
        SD["Sensor Drivers"]
        LC["LED Controller"]
    end

    P --> MCU
    MCU --> TS
    MCU --> LD
    TS --> SD
    SD <--> |"Measure Temperature" | MCU
    MCU --> |"Display to Screen" |LC
    LC --> LD

```

## Project Structure Tree
DIYThermometer/
├── docs/
│ ├── hardware/
| |  ├── architecture.md
| |  ├── wiring.md
| |  └── serial-protocol.md
│ └── requirements.md
├── firmware/
│ ├── src/
| |  ├── main.ino
| |  ├── temp.ino
| |  └── LED.ino
│ └── tests/
│   ├── test_LED.ino
│   └── test_temp.ino
├── README.md
└── LICENSE

## License
  This is obviously a copyleft document so that people have a base to build off of to learn temperature readings.
