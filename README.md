# zephyr-ble-central-and-peripheral-hr
BLE device with Central and Peripheral roles concurrently

Tested on nrf52840-dk (PCA10056).

### The nrf52840-DK acts as both ble peripheral and central concurrently. 
- Peripheral -  Advertises `ZEPHYR RELAY` and exposes heart rate GATT service.
- Central - Scans for hear rate monitors, once connected reports heart rate readings 

## Building
``` 
west build -b nrf52840_pca10056
```

# Flashing 
```
west flash && nrfjprog -r
```
