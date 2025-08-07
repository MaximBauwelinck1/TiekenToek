# TiekenToek
This repo contains the hardware setup used to stream the video from https://tiekentoek.be

[Front end repo](https://github.com/MaximBauwelinck1/TiekEnToekFrontEnd)

![TiekEnToekCamera1](https://github.com/user-attachments/assets/e36239b6-cb58-4ae3-83f9-c98bb9f3ace8)



## Goal
The goal of this project was to stream video from a remote location where internet connection and a power outlet where absent. 

## Soloution
To supply everything of power I used 3 solar panels wich give me a total of 5v and ~950mA when fully lit(added extra ones). This would charge the batteries in ~8hrs in optimistic conditions. To handlle the wifi connection I ended up choosing an 4g dongle with an overpriced sim card data package from Lyca. 

1) Battery capacity
   3.7 V * 6.9 Ah = 25.53 Wh
2) Solar panels
   5 V * 0.95 Ah = 4.75 W
   In optimistic conditions the solar panels will yield 4.75W in optimistic conditions.
3) Realistic charging time
   The TP4056 module will have around a ~80% efficiency because of heat loss. And besides that we account for another loss of about 15% due to clouds, angle of the sun and heat conversion. So 0.65 * 4.75 W = 3.09 W . The total charging time will be 25.53 Wh / 3.09 W = 8.26hrs.

## TODO
- Replace pi Zero 2W with a more powerfull Pi. CPU cant handle the video encryption and needs to be send in a lower res etc.

## prerequisites
**Hardware**
- 1x Pi Zero 2W
- 1x Pi Pico
- 1x [Arducam Rev.C OV5647](https://www.raspberrystore.nl/PrestaShop/nl/camera/558-arducam-revc-ov5647-cs-mount-cameramodule-4mm-lens-ls-2716.html)
- 1x [4g dongle](https://www.bol.com/be/nl/p/4g-wifi-dongle-glofi-wingle-f8-dongel-voor-draadloze-4g-150mbps-wit/9300000181539362/?Referrer=ENTcli_shipment_confirmation_standard_7131a3af-d2c5-4571-b5da-8ea3d4253ac7)
- 1x [Step up converter MT3608](https://www.az-delivery.de/nl/products/mt3608-dc-dc-step-up-modul-1)
- 1x [BMS module TP 4056](https://www.az-delivery.de/nl/products/az-delivery-laderegler-tp4056-mini-usb)
- 2x [Li-ion battery 3.7 V 3450 mAh](https://www.123accu.nl/Samsung-INR18650-35E-Li-ion-batterij-3-7-V-3450-mAh-8A-i49699.html)
- 1x [ultrasonic sensor wpse306N](https://whadda.com/product/ultrasonic-distance-sensor-wpse306n/)
- 1x Mosfet IRL540N
- 1x 330 Ω
- 1x 10 KΩ
- 3x solar panel 5V 1.5W 220mA
- 1x sim card

**Software**
-  sim card subscription with data
- [Systemd service running on home server handling pipeline.](https://github.com/MaximBauwelinck1/TiekenToek/blob/main/scripts/Streaming%20service%20home%20server)
- Nginx server
- [SystemD service running on remote pi zero 2W](https://github.com/MaximBauwelinck1/TiekenToek/blob/main/scripts/Streaming%20service%20zero%202W)
- [Pico Py script](https://github.com/MaximBauwelinck1/TiekenToek/blob/main/scripts/Pico)

## Electrical wiring
 <img width="3000" height="4000" alt="image" src="https://github.com/user-attachments/assets/21131d52-774a-42d7-9d1d-e3a14c921259" />

 ![testt](https://github.com/user-attachments/assets/7d1da792-a10b-483b-8724-43d90a014e98)

 ![20250804_232245](https://github.com/user-attachments/assets/3bbb4652-8cbd-4336-ab5d-94cf6c0c4958)

<img width="4000" height="3000" alt="image" src="https://github.com/user-attachments/assets/4f2d1435-39e9-43cc-9dbd-3c3e4c61ee9f" />

![20250804_232429](https://github.com/user-attachments/assets/24cb8b6f-726d-41a7-872b-b4dabfffd295)

![rn_image_picker_lib_temp_d2c5df95-f211-45a0-92c2-a630b6bdf154](https://github.com/user-attachments/assets/781b313e-acba-4d24-af19-ca78ffa1dbc0)




 
