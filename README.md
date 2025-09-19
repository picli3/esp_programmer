# ESP32 Prog Lite

This module was designed to optimize the programming of ESP32 devices in production environments. It emerged as a solution to a common problem: the need to efficiently and cost-effectively program electronic products that don't require a USB port for final operation.

|             |                 |
|:------------:|:----------------:|
| ![](doc/ESP_32_Programer-1.png)         |![](doc/ESP_32_Programer-0.png)|



## The USB problem in production

For devices that run on alkaline batteries or are programmed only once at the factory, a USB connector and its integrated serial converter, such as the popular CP2102N, represent an unnecessary cost. In mass production, these components add up to a considerable expense. For example, in a production run of 1,000 units, a converter at $2 USD per piece increases the total cost by $2,000 USD, not including the other associated components and the space they take up on the board.

In a real-world case, a customer looking to update their PCB design had a USB-C converter on their board. By eliminating these circuits and offering our solution, which uses Pogo-Pin clips, we were able to significantly reduce their costs and production time.

## A simple and efficient design

Our main objective was to simplify the programming process, making it as small and efficient as possible. We were inspired by the **ESP-programmer**, a device known for its JTAG programming and debugging capabilities. However, our goal was not to replicate all of its features, but rather to create a minimalist tool focused exclusively on production programming that would allow for seamless integration and rapid adoption on any assembly line.

This approach has allowed us to develop a programmer that offers a low-cost, high-performance solution for mass production of ESP32-based products.

## Why choose this programmer?

* **Cost savings:** Eliminates the need for integrated USB-to-serial converters on each board, dramatically reducing unit costs in mass production.

* **Space optimization:** Its compact design frees up valuable PCB space, ideal for products with size constraints.

* **Production efficiency:** Enables quick and easy programming using Pogo-Pin connectors, streamlining the manufacturing process.

## Generate panel

To do this it is required [Kikit](https://github.com/yaqwsx/KiKit?tab=readme-ov-file)

```sh
kikit panelize \
    --layout 'grid; rows: 6; cols: 2; space: 2mm' \
    --tabs 'fixed; width: 3mm; vcount: 2' \
    --cuts 'mousebites; drill: 0.5mm; spacing: 1mm; offset: 0.2mm; prolong: 0.5mm' \
    --framing 'railstb; width: 5mm; space: 3mm;' \
    --tooling '3hole; hoffset: 2.5mm; voffset: 2.5mm; size: 1.5mm' \
    --fiducials '3fid; hoffset: 5mm; voffset: 2.5mm; coppersize: 2mm; opening: 1mm;' \
    --text 'simple; text: MaykolRey.com; anchor: mt; voffset: 2.5mm; hjustify: center; vjustify: center;' \
    --text2 'simple; text: Created on {date}; anchor: mb; voffset: -2.5mm; hjustify: center; vjustify: center;' \
    --post 'millradius: 1mm' \
    ESP_32_Programer.kicad_pcb panel/panel.kicad_pcb
```
## Licence

![](doc/oshw_facts.png)

Author: Maykol Rey
