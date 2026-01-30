# Bronica ETR Lens Pinout
This document serves to explain he pinout and electrical working of Bronica ETR lenses, special thanks to Oscar from Panomicron.

All Bronica ETR Lenses have 6 pins at the top of the lens which connect to the body of the camera. These have the following functions:

![alt text](https://github.com/user-attachments/assets/7240a087-08a1-44a9-baec-e1f016c5d00a)

| Pin | Function |
| :--- | :---: |
| 1 | Ground |
| 2 | Unknown |
| 3 | Aperture |
| 4 | Flash trigger |
| 5 | Delay |
| 6 | Aperture |

## Lever
The lens lever, marked **L** in the above image is used for preemptively closing the shutter, starting the shutter firing sequence and recocking the lens. As the lever moves down from the default position (shown in the image indicated by a green dot), the sequence is as follows: 

1. As soon as the lever is moved downwards, the shutter will start closing gradually.
2. When the lever has moved down about 4mm from the default the shutter will be fully closed & aperture blades will be set to the value set on the ring.
3. When the lever is about 3mm from the lowest position it can reach, there's some extra resistance and when this is overcome, the shutter will start firing.
4. The shutter will be open for ~1/500th of a second before closing unless delayed by providing a high signal (>3,3V) to pin 5
5. When the lever is moved up back to the default position, the lens will be recocked.

## 3 & 4. Flash Trigger
These pins are normally interconnected, but interupted for a short time (regarless of shutter speed) when the shutter is fired.

## 5. Delay
When the shutter is fired, it will stay open for as long as a high (3.3V or higher) signal is provided to this pin, controlling the shutter speed. By accurately sitting the signal on this pin to high you can control the shutter speed to any arbitrary value, though it's important to remember that the lens has a mechanical fallback of ~1/500th of a second so it cannot be forced to close any faster than that. I'd be careful keeping the shutter open for very long periods as it might heat up the electromagnets in the shutter. 

## 6. Aperture
This pin changes resistance based on the aperture set on the lens in ~200 Ohm steps per increment. 
In the Bronica Zenzanon 75mm 2.8 [service manual](https://ianbfoto.com/downloads/Repairs/Bronica-ETR-75mm--Repair-Manual.pdf) we can find the correct resistance values:

| Diaphram (F-Stop)| Resistance (Ohm) |
| :--- | :---: |
| 2.8 | 1330 ~ 1470 |
| 4 | 1140 ~ 1260 |
| 5.6 | 950 ~ 1050 |
| 8 | 760 ~ 840 |
| 11 | 570 ~ 630 |
| 16 | 380 ~ 420 |
| 22 | 190 ~ 210 |

Note: Bronica ETR lenses MC lenses use the above aperture settings, but PE lenses added half-indents, I'm assuming the resistance interval for those would be ~100 Ohms, but I haven't confirmed this yet.
