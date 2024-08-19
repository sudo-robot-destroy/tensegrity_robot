# tensegrity_robot
A repository to track the development of a robot with tensegrity wheels

## Main Design Goals
The main idea is to investigate making a ground vehicle capable of being dropped from a drone without being damaged with the following requirements:
* The vehicle should also be able to drive over rough terrain like high grass, forest floor and climb steps.
* It should also either be able to drive upside down or easily flip itself over.
* The vehicle should be light weight and made using DIY components like off the shelf parts and 3D printing.

## Background
The first design is motivated by [[1]](https://jiefengsun.github.io/pdfs/spiegel2023shape.pdf).
As mentioned in the paper, some shortcomings of their design are sticks get stuck in wheels since they're open, and it tips over easily since there are only two wheels. The first design trial will use similar wheels but will have 4 wheels in a skid steer layout. If stuck sticks are a problem I might look into using closed wheels although I'm not sure if they're work great. 

Construction of tensegrity wheels is detailed in [[2]](http://best.berkeley.edu/wp-content/uploads/2017/09/DETC2017-68264-1.pdf).

## Rough ideas
* The wheels will be TPU and carbon fiber rod.
* The rest of the body will be a combination of carbon fiber rod and 3D printed TPU and PETG parts.  
* The first design will use simple electronics:  
  * an RF receiver
  * 4-in-1 ESC
  * Two brushless motors for drive
  * A single servo for collapsing the wheels?
  * A lipo battery (3s?)

## First design attributes
For the first design, I'll just copy the wheels from [1] as much as possible, here is what they used:  
### Wheels: 
* Carbon rod diameter: 2 mm  
* Carbon rod length (l<sub>r</sub>): 130 mm, 6 rods/wheel so 24 are needed.  
* Rod caps: abrasion-resistant TPU - Cheetah 95 A  
* Rod cap length: 12 mm
* Cable material: TPU - Ninja-flex 85 A  
* Wheel hub material: Nylon-X (carbon fiber-enhanced filament)  
* Cable cross thickness: 1.5 mm  
* Cable width: 1 mm 
* Cable length (printed, 0.9(0.6l<sub>r</sub>)): 70.2 mm  

### Collapsing mechanism:  
* Motor:[Pololu: 1595](https://www.pololu.com/product/1595) (stall torque - 12 kgcm) 
* Cable: Nylon

### Drive train:
* Drive motors: [Pololu: 4794](https://www.pololu.com/product/4794) with 3:1 extra
* Stall torque: 5.5 kgcm x 3 = 16.5 kgcm
* Drive bearings: [Uxcell: 626-2RS](https://www.amazon.com/uxcell-626-2RS-Bearing-6x19x6mm-Bearings/dp/B07TLKGDJ6/ref=sr_1_1?adgrpid=1344704363644125&dib=eyJ2IjoiMSJ9.x1zuH9vG9i6w9yyZxxelhKFHBJv1FImEytNKyra2iieqsGlIQHr_YcpgpsRq1ntwg2POE2qNnk7kJOlOErjvGNUfOu9bqDvpLv7MIL15sLazMoBLB1VN6tKKrK0EBtonTXtCbzyRt-Rn_pv_APE44Cb99HefonlcycK84kqFuoWM4p9zmjguNTPugiKeqFdpJQCNBz4dlHA4jKkQlb5CCmtBk0v0Ujq-rbDEv48NmLUkHT34n9R9nwxNZ6WYRMqnDDO1PjYLvGSuXfwMlV-O1V8TBxoAKj9OkR3AmjHwWFo.bwMaQiG9b17b8zCjj_6ESoTV7-W4cOivLljPzqzLtxg&dib_tag=se&hvadid=84044284024935&hvbmt=bp&hvdev=c&hvlocphy=82074&hvnetw=o&hvqmt=e&hvtargid=kwd-84045029114616%3Aloc-190&hydadcr=3699_13538776&keywords=uxcell%2B626-2rs&msclkid=6f97d1b3fdcb1997ce27b7719cfc8239&qid=1724015292&sr=8-1&th=1) 
* Battery: 2S Lipo
* Motor driver: [Pololu: 2135](https://www.pololu.com/product/2135) (also used for collapsing) 

## Shopping list
* Carbon fiber rods: [400 mm x 10 from Fielect for $12.99](https://www.amazon.com/Fielect-Diameter-Carbon-Straight-Airplane/dp/B083LC917H/ref=sr_1_1?crid=8SJAFYCP4G14&dib=eyJ2IjoiMSJ9.bYibJqgoi3mkfRk6BZZjEg.0A8NhV84t7Ulu0X0udCyh-6fuVbvYyuh7B3RlN_4nkc&dib_tag=se&keywords=B083LC917H&qid=1724028988&sprefix=b083lc917h%2Caps%2C112&sr=8-1)  
* TPU, 85A: [Siraya Tech Flex TPU for $31.99](https://www.amazon.com/Siraya-Tech-Flex-Filament-Moisture-Resistant/dp/B0CP213ZMG/ref=sr_1_4?crid=2P2QDYPA6NI2O&dib=eyJ2IjoiMSJ9.1OVszLtutl2C0lBZMNOByStRyXq34ieZhvdqGd2L8pRA4_tO247coIwjTxtk9Ql_zMECo4W9dawgCc-nvOIwvZGSc1Rx3wTbBCmtBdkAOVccCECbczInfado6Ex-pgNUx0dP8IqEJXepjA1_91v11LI6CB6wadgyYMqdWfFdDEyvkWsD0KPWX6ZN284Oe2OySjReJaKD4fCh2PSDQHsTtuZM24o-VVH0PGfCF6MkmkJJtgZdJ358cSx-rR-ZsIDXFv7wFGsuqqDmCKFiMzaViHzaOoPfKeGBsnFUKc54OpU.nBBuHVxrA8AR0x9tfsa4DmA__dW5v1xffexHGbtQRQc&dib_tag=se&keywords=3d%2Bprinter%2BTPU%2Bfilament%2B85a&qid=1724029373&refinements=p_36%3A-4200%2Cp_72%3A1248921011%2Cp_85%3A2470955011&rnid=2470954011&rps=1&s=industrial&sprefix=3d%2Bprinter%2Btpu%2Bfilament%2B85a%2Caps%2C123&sr=1-4&th=1) 

## TO-DOs:
* Pick out a TPU filament for the Bambu X1

## References:
[1] "A Shape-Changing Wheeling and Jumping Robot Using Tensegrity Wheels and Bistable Mechanism" https://jiefengsun.github.io/pdfs/spiegel2023shape.pdf

[2] "Modular Elastic Lattic Platform for Rapid Prototyping of Tensegrity Robots" http://best.berkeley.edu/wp-content/uploads/2017/09/DETC2017-68264-1.pdf
