# zephyr-ble-central-and-peripheral-hr

BLE device with Central and Peripheral roles concurrently.

This project was tested on nRF52840-DK (PCA10056).

### The nrf52840-DK acts as both ble peripheral and central concurrently.

* Peripheral -  Advertises `ZEPHYR RELAY` and exposes heart rate GATT service.
* Central - Scans for hear rate monitors, once connected notifies heart rate readings 

## Requirements

- Two nRF52840-DK, call it **Device-A** and **Device-B**
- A mobile phone with `nrf Connect` app.

## How to?

- Clone this repo, build and flash it on **Device-A**
- Program **Device-B** with `samples/bluetooth/peripheral_hr`
- Install `nrf Connect` app from Play Store or App Store
- Device-A scans for Heart Rate Monitor and advertises as `ZEPHRY RELAY` exposing Heart Rate GATT service.
- Device-B advertising as Heart Rate Monitor connects to Device-A
- On the mobile app look for `ZEPHRY RELAY` and connect to it. Enable notifications to receive heart rate readings from Device-A

## Building

``` 
source <path>/zephyr/zephyr-env.sh
west build -b nrf52840_pca10056
```

# Flashing 
```
west flash
```
