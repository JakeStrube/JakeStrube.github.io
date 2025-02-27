---
title: Power Budget
---

## Overview

Below is the power budget for the HMI subsystem. It includes the major component and the microcontroller and estimates how much power it would consume and how long the battery would last with just the one subsystem.

### Power Budget

![Power Budget](Power_Budget.png)

### Explanation

The power budget above shows that the minimum amount of battery life expected if all systems were running at their highest power consumption would be 3.1 hours of battery life using the 6 PX1500 AA batteries all connected in series. Each of these batteries according to their data sheet, which is linked below, has a capacity of 3.112Ah and produce 1.5V. When all 6 are aligned in series their combined voltage jumps to 9 volts while keeping the 3.112Ah of battery life. The expected battery life of the subsystem should be more than the 3.1 hours predicted because the subsystem will not be running at max power for the whole 3 hours during its actual operation.

-[Battery datasheet](PX1500.pdf)