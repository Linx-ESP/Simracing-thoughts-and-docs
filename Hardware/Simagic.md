# Alpha EVO series

Manual: [Simagic](https://cdn.shopify.com/s/files/1/0764/6756/8943/files/SIMAGIC_Alpha_EVO_UM_EN.pdf?v=1750675937), [archive.org](https://archive.org/details/simagic-alpha-evo-um-en)

- **Outputs**: 
  - USB-B: 
    - Main connection
  - USB-C: 
    - QR passthrough (no need for Maglink for GT NEO)
    - 6 pin front pads

- **Inputs**:
  - Power plug: Need to measure, inner positive. Both base and stock PSU: 48V 5.,25A   
  - 4x RJ45: CAN-FD data
  - +1x RJ45: CAN-FD for Emergency stop (seems like it can be used for more than the E-Stop)   
  - 2x RJ45: CAN-FD + USB data
  - 3x USB-A: CAN (non-FD, no USB data)
 
-  **Additional inputs**
  - 6 pads on the front: Supossedly for magnetic dashboard (not yet released)

## Quick Release  

<img width="204" height="256" alt="qr" src="https://github.com/user-attachments/assets/3c9d023e-fca3-45e4-aa1c-b6d2cb917db5" />

**Pinout**

 1. Unused, not wired. See [Fig.11](https://device.report/m/f126831834026bdba767825189e33fd79168db67a7ac37a613d76328ecbc425b)
 2. **5V**
 3. **GND**
 4. USB Data-
 5. CAN (-FD?)
 6. CAN (-FD?)
 7. USB Data+

External sources:
- https://www.reddit.com/r/Simagic/comments/1lvrenl/alpha_evo_usb_passthrough_pins
- [Youtube: Dan Suzuki - Simagic Alpha EVO Wheelbase Review](https://youtu.be/pInQ37QII1g?si=CptPgroDBuGtOyhN&t=781)

Pins 1 and 3 have no continuity and Pin 1 doesn't seem to be neither GND or Voltage.   
Aliexpress/3rd party QRs usually only have 5V and GND. One with full USB would be lovely for DIY.    
  
If you have a Simagic NEO wheel you can tape pin 5 and 6 to force USB through the passthrough, and 4,5,6,7 to force wireless (as it was in the non-EVO).  
Why did they put CAN in there? 
  
**Extra**  
  
- Pogo pins: from PCB; 4.0mm compress, 5.5mm extended 
  
## Front Connectors

Pads: 
- 2,5mm or 2,54mm pitch.
- 1,5mm diameter

**Pinout**  

Image source: https://fccid.io/2AWJ8-ALPHA-EVO/Internal-Photos/Internal-photos-7699578.pdf & https://device.report/m/f126831834026bdba767825189e33fd79168db67a7ac37a613d76328ecbc425b

<img width="368" height="180" alt="image" src="https://github.com/user-attachments/assets/65c7da21-ecef-48df-b19a-d23e66ed365b" />

Left to Right 
- **5V**
- **USB Data+**  
- **USB Data-**  
- CAN-FD Low
- CAN-FD High
- **GND**

Rear PCB cabling from [Boosted Media](https://www.youtube.com/watch?v=xHefYsMJs54&t=1925s)  
<img width="284" height="294" alt="image" src="https://github.com/user-attachments/assets/a1b0ddec-fe4f-4745-92ab-8ca793696e85" />



## Paddle shifter modules

- Pinout [r/Simagic](https://www.reddit.com/r/Simagic/comments/1k9zxhn/help_simagic_dual_paddle_shifter/)
<img width="204" height="256" alt="image" src="https://github.com/user-attachments/assets/ed258c3c-84f4-4817-bd19-8274e2b1b9df" />



# Teardowns / Dissassemblies

## Partial

- GT Neo Hub [r/Simagic](https://www.reddit.com/r/Simagic/comments/1clidwj/simagic_gt_pro_hub_disassembly/)
- GT Neo [YT: Simagic Official](https://www.youtube.com/watch?v=_ftnGmK0h7M)

## Components used

### Confirmed

### Guessed:

- *Funky Switch* / 7-way encoder: [ALPS RKJXT1F42001](https://tech.alpsalpine.com/e/products/detail/RKJXT1F42001/)
- RGB Buttons: [CTS 228C series](https://eu.mouser.com/datasheet/2/96/CTS_Switches_Tactile_228C_Series_Datasheet-1371171.pdf) 
  - Sadly no stock at lscs.com for JCLPCB assembly
  - Similar: HOOYA TC-1196A-RGB-E-01
  - Similar: Khon TSL06351-070D831DE-RGB


### Negative

- Rotary Encoders:
 - ALPS EC11 series: No unit with 12 notches/indents

