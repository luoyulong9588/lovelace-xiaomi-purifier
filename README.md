fork 自https://github.com/iwzoo/lovelace-xiaomi-purifier

###  小米空气循环扇的属性有变化，导致原插件不能使用。修改适合小米空气循环扇，功能及使用方法同源码。


```angular2html

preset_modes: Auto, Sleep, Favorite
preset_mode: Auto
model: zhimi.airp.rma3
lan_ip: 192.168.4.201
mac_address: D4:F0:EA:52:90:F0
entity_class: MiotFanEntity
home_room: 大学时代 客厅
miot_type: urn:miot-spec-v2:device:air-purifier:0000A007:zhimi-rma3:1
air_purifier.on: true
air_purifier.fault: 0
air_purifier.mode: 0
aqi.aqi_updata_heartbeat: 300
custom_service.moto_speed_rpm: 420
filter_used_time_dbg-9-2: 456
air_purifier_favorite.fan_level: 4
physical_controls_locked: false
screen.brightness: 1
alarm: true
filter.filter_life_level: 87
filter.filter_used_time: 456
filter.filter_left_time: 126
environment.relative_humidity: 73
environment.pm2_5_density: 13
environment.temperature: 11
environment.air_quality: 0
state_updater: lan
sub_entities: custom_service-9.moto_speed_rpm-1, alarm-6.alarm-1, screen-7.brightness-2, environment-3.relative_humidity-1, environment-3.pm2_5_density-4, environment-3.temperature-7, environment-3.air_quality-8, filter-4.filter_life_level-1, filter-4.filter_used_time-3, filter-4.filter_left_time-4, physical_controls_locked-8.physical_controls_locked-1
friendly_name: Xiaomi Smart Air Purifier 4 Lite Air Purifier
supported_features: 56


```


# lovelace-xiaomi-purifier
Xiaomi Purifier lovelace card with css animation

## Extra Features
1. compact view to show temperature and humidity 
1. button to turn on/off buzzer
1. double click to swith led 
1. hold "Favorite" button to adjust fan speed


## HACS Installation
1. HACS -> Settings -> Add custom repository <-> Plugin
2. Find 'xiaomi purifier' in HACS Plugins
3. Install and add to Lovelace

## Manual Installation
1. Download `xiaomi-purifier.js` to `www/plugins/xiaomi-purifier.js`
1. Add to lovelace resources
   ``` yaml
   resources:
    - url: /local/plugins/xiaomi-purifier.js
      type: js
   ```
## Add lovelace card 
  ``` yaml
  type: 'custom:xiaomi-purifier'
  entity: fan.anyid
  title: name of the purifier device
  advanced: #optional (true for showing temperature and humidity in the middle, otherwise shows in green panel)
  ```
  
### Language 
Displays English texts by default, for Chinese language users, add 
```
language: chs
``` 
to card configuration for displaying texts in Chinese.

Add translations to get your own language support. 
``` 
translate: 
   'Good': '优',
   'Moderate': '良',
   'Mild Unhealthy':'轻度污染',
   'Unhealthy': '中度污染',
   'Very Unhealthy': '重度污染',
   'Hazardous': '严重污染',

   'Air Purifier': '空气净化器',

   'On': '开启',
   'Off': '关闭',

   'Set speed': '设置速度',
   'Device turned on': '开启设备',
   'Device turned off': '关闭设备',
   'Indoor AQ': '室内空气',

   'Auto': '自动',
   'Silent': '睡眠',
   'Favorite':'最爱',

   'Temperature': '温度',
   'Humidity': '湿度'

```


## Credits
[shaonianzhentan](https://github.com/shaonianzhentan/lovelace-air-filter) (Original Author)
