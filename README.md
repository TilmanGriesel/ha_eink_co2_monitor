# E-ink CO2 Monitor

A battery-powered ESPHome device that displays air quality data and temperature on a 2.13" e-ink screen.

![product](https://github.com/TilmanGriesel/ha_eink_co2_monitor/blob/main/docs/product.png?raw=true)

## Features

- **Air Quality Monitoring**: Displays CO2 levels in ppm with temperature and humidity readings
- **Ultra Low Power**: Uses deep sleep mode with 30-minute update intervals to maximize battery life
- **Smart Sleep Schedule**: Automatically sleeps from 8 PM to 5 AM to conserve power during off-hours
- **Battery Monitoring**: Shows current battery voltage and percentage with low battery warning display
- **Wireless Updates**: Over-the-air (OTA) firmware updates via Home Assistant
- **Always-On Display**: E-ink technology provides continuous visibility without power consumption

## Hardware

- **Microcontroller**: ESP32 Feather board
- **Display**: Waveshare 2.13" e-ink display (TTGO-B74 model)
- **Power**: Battery-powered with voltage monitoring on pin 35
- **Connectivity**: Wi-Fi for Home Assistant integration
- **E-Ink + Controller**: https://www.aliexpress.us/item/3256802876849280.html
- **Case**: https://www.printables.com/model/412141-lilygo-ttgo-t5-213-case

## Home Assistant Integration

Retrieves sensor data from Home Assistant entities:
- Office CO2 levels from weather station
- Temperature and humidity readings
- Publishes battery status back to Home Assistant

## Display Layout

**Normal Mode:**
- Large CO2 reading in ppm
- Temperature and humidity in top-right corner  
- Vertical accent bar on the left

**Low Battery Mode:**
- Battery icon warning when voltage drops below 3.5V

## Power Management

- **Sleep Duration**: 30 minutes between updates
- **Active Time**: 10 seconds per wake cycle
- **Night Mode**: Deep sleep from 8 PM to 5 AM
- **Battery Life**: Optimized for weeks/months of operation on single charge

## Configuration

The device integrates seamlessly with Home Assistant and requires minimal configuration. All sensitive credentials are stored in a separate secrets file for security.