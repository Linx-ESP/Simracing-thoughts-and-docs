# Alpha EVO series

Manual: [Simagic](https://cdn.shopify.com/s/files/1/0764/6756/8943/files/SIMAGIC_Alpha_EVO_UM_EN.pdf?v=1750675937), [archive.org](https://archive.org/details/simagic-alpha-evo-um-en)

- **Outputs**: 
  - USB-B: 
    - Main connection
  - USB-C: 
    - QR passthrough (no need for Maglink for GT NEO)
    - ¿Accesories like the 6 pin front connector for the "dashboard"?

- **Inputs**:
  - Power plug: Need to measure, inner positive. Both base and stock PSU: 48V 5.,25A   
  - 4x RJ45: CAN-FD data
  - +1x RJ45: CAN-FD for Emergency stop (seems like it can be used for more than the E-Stop)   
  - 2x RJ45: CAN-FD + USB data
  - 3x USB-A: CAN (non-FD, no USB data)
 
-  **Additional inputs**
  - 6 pads on the front: Supossedly for magnetic dashboard (not yet released)

### Quick Release  

![simagic-qr-wheel-side-numbered](https://github.com/user-attachments/assets/3c9d023e-fca3-45e4-aa1c-b6d2cb917db5)

**Pinout**

 1. ¿?
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
  - Mention to HOOYA TC-1196A-RGB-E-01


### Negative

- Rotary Encoders:
 - ALPS EC11 series: No unit with 12 notches/indents

