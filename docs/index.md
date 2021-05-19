# Gfrör.li Documentation

## RN2483

See [`rn2483.md`](./rn2483.md).

## STM32L071

See [`stm32l071.md`](./stm32l071.md)

## Antenna / RF

See [`rf.md`](./rf.md)

## Debugger

We use the Segger JLink debugger.

The adaper used is the
[ARM-JTAG-20-10](https://www.digikey.ch/product-detail/de/olimex-ltd/ARM-JTAG-20-10/1188-1016-ND/3471401)
by OLIMEX.

- [Digikey](https://www.digikey.ch/product-detail/de/olimex-ltd/ARM-JTAG-20-10/1188-1016-ND/3471401)
- [Olimex Store](https://www.olimex.com/Products/ARM/JTAG/ARM-JTAG-20-10/)
- [Schematics](../datasheets/ARM-JTAG-20-10_latest-schematic.pdf)

## Powering the PCB

There are 3 ways to power the PCB:

- Battery power (3.3-4.2V)
- USB (5V)
- Debug probe (5V)

To choose the power source, the jumper J7 needs to be set appropriately.

If you want to power the board through the JLink debug probe, the solder bridge
R1 on the OLIMEX adapter must be closed. Then 5V power will be [supplied on pin
7 of the connector](../datasheets/ARM-JTAG-20-10_latest-schematic.pdf).

### Power Consumption

The peak power consumption is:
 * RN2483: ~40mA
 * STM32L071: ~10mA (IDD is 7.4mA according to datasheet Table 29.)
 * LEDs: ~10mA
 * SHTC3: ~1mA
 * DS18B20: ~1.5mA

So if we calculate with a peak power consumption of 100mA we should be on the safe side.
