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
 4. USB
 5. CAN (-FD?)
 6. CAN (-FD?)
 7. USB

Pins 1 and 3 have no continuity and Pin 1 doesn't seem to be neither GND or Votlage
Aliexpress/3rd party QRs usually only have 5V and GND. One with full USB would be lovely for DIY.    
  
If you have a Simagic NEO wheel you can tape pin 5 and 6 to force USB through the passthrough, and 4,5,6,7 to force wireless (as it was in the non-EVO).  
Why did they put CAN in there?  
  
I don't know if it is a true passthrough or not. Should be easy to check putting a USB Device in the QR.  
