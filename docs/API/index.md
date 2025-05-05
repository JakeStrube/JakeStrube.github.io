---
title: API
---

## Overview

The Application Programming Interface (API) is the connection between computers. We will use the API system to communicate between each team memebers subsystem. Outlined below is how the team plans to communicate with each other.

## Message Protocol

### Messages That I Send

These are messages that I will send out to my teammates. Each table shows the message structure with along with a descrioption of how it works and who will recieve the message.

#### Change Following Distance
| Type | Byte 1 | Byte 2 |
| ---- | ------ | ------ |
| Variable Name | message_type | set_distance |
| Variable Type | uint8_t | hex |
| Min Value | 0 | 0 |
| Max Value | 9 | 100 |
| Example | 1 | 20 |

- This message sets the distance at which the robot is supposed to stay away from the object it is detecting. The message begins with byte one, the message type, allowing the reciever to sort the message easier, then byte 2 is the value of the distance that the robot is supposed to keep away from the object its tracking. The set_distance value does not directly communicate with sensors or motor it only states the distance goal that the robot is supposed to keep. This message will be sent to both Andrey and Divine's subsystems that they will use accordingly. The values for the distance is in mm and it is incremented from 0 to 100 in increments of 20.

#### Change Motor Speed
| Type | Byte 1 | Byte 2 |
| ---- | ------ | ------ |
| Variable Name | message_type | motor_speed |
| Variable Type | uint8_t | hex |
| Min Value | 0 | 0 |
| Max Value | 9 | 100 |
| Example | 0 | 60 |

- This message changes the speed at which the motors will move at. The message begins with the message type allowing the reciever to sort the message easier, then byte 2 is the target speed at which the motor will travel at. The speed value does not control the motor directly just states at what speed all the motors will move at. The message will send to both Divine and Jacob's subsystem and they will update accordingly. The values for the speed is in mm and it is incremented from 0 to 100 in increments of 20.

### Messages I Recieve

These are the messages that I can recieve from my teammates. The tables show the message structure along with a description of the message and who I would recieve the message from.

#### Update Displayed Following Distance
| Type | Byte 1 | Byte 2 |
| ---- | ------ | ------ |
| Variable Name | message_type | display_distance |
| Variable Type | uint8_t | hex |
| Min Value | 0 | 0 |
| Max Value | 9 | 100 |
| Example | 1 | 20 |

- This message that I recieve will allow my system to update the displayed speed on the OLED screen. Byte 1 is the message type allowing my system to easily figure out what the message will be. Then byte 2 is the new distance that I will be displaying OLED screen. I will recieve this message from Divine.

#### Update Displayed Motor Speed
| Type | Byte 1 | Byte 2 |
| ---- | ------ | ------ |
| Variable Name | message_type | display_speed |
| Variable Type | uint8_t | hex |
| Min Value | 0 | -100 |
| Max Value | 9 | 100 |
| Example | 0 | 60 |

- This message that I recieve allows my system to update the displayed motor speed to the OLED screen. Byte 1 is the message type allowing my system to easily sort the message. Byte 2 is the new speed that the OLED screen will be displaying. I will recieve this message from Divine.


### Other Types of Messages

- Any message that I recieve that I do not have a protocol to handle the system will delete the message to help clean up the system and reduce clogging.
- If I recieve a message that I sent but no one recieved it I will delete the message so that the message is not cycling forever clogging the message system.
- Any message that I recieve that is not directed towards me but is directed to another teammember will be passed over to the next teammate in the subsystem so that they may recieve the message.
- If a message is addressed to someone not in my team then the system will delete the message preventing clogging due to dud messages.
