# AR-Indoor-Navigation-System
Indoor navigation using Unity and Vuforia SDK. Prototype at Faculty of Information Technology, KMITL
This project is in development. | Senior project for Bachelor of Science (Information Technology) King Mongkut's Institute of Technology Ladkrabang 
-sorry for my bad English

## Description Overall
This project are navigation system on android. Point your mobile's camera to building for find marker images taht resamble with image in database. When found, it will show AR that contains data of that position (if not in navigate mode).
User can known thier position and rotation direction from Top-view map. and can start navigate mode by choosing destination of that building from Search page. When in navigation mode and point your camera to marker, It will show AR red arrow point to next node. And will show AR green checked when reach destination.

## Abstract from my paper (may be easier to understand)
– Augmented reality based indoor navigation system running on a smartphone is proposed to be used for in-building navigation. The system uses a built-in camera to capture the image of surroundings, detects a natural marker in the image, and calculates the pose of the camera with respect to the marker. The position and orientation of the camera (which are the same as the smartphone itself) with respect to the indoor map are then determined using the pose information of that marker—note that each marker must be pre-registered with pose information in the system. Once the destination is specified by the user, the shortest path to that destination will be calculated and the arrow pointing along the path to the destination will be augmented on the scene. The information message explaining the route will also be annotated on the screen and be read out to help guide users to the destination. In addition, the system can display a top view map of building showing current position and facing direction of the user, and drawing the route to the destination—the top-view mode makes a better understanding and experience for the user. 

## ScreenShot
on start app[1] and found marker[2] marker will show like [3] in Top-view page
![start](https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav04board.jpg =250x355) ![marker show data of that pos](https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav05board.jpg =250x355) ![top view in idle mode](https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav08top.jpg =250x355)

Search page (I Search for room 317)
<img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav06search.jpg" alt="search page" width="150"/> <img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav07search.jpg" alt="search page when type something" width="150"/>

before navigate will have dialog of destination's data and navigate button
<img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav11beforechoose.png" alt="first room" width="150"/>

in navigate mode (purple)
<img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav01arrow.jpg" alt="first room" width="150"/> <img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav02arrow.jpg" alt="second room" width="150"/>

Top-wiew map (relate below)
<img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav09top.jpg" alt="top view first room" width="150""/> <img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav10top.jpg" alt="top view second room" width="150"/>

when reached destination
<img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/arnav03tick.jpg" alt="reached" width="150"/>

we can also navigate complex map using dijkstra's algorithm (this is my test map)
<img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/complex1.png" alt="reached" width="150"/> <img src="https://raw.githubusercontent.com/fasterac/AR-Indoor-Navigation-System/master/ReadmeComponents/complex2.png" alt="reached" width="150"/>


------------------------------------------

# ระบบนำทางในอาคารด้วย AR
ใช้ Unity และ Vuforia ทดสอบเริ่มต้นที่อาคารคณะไอทีลาดกระบัง
โปรเจคอยู่ในระหว่างการพัฒนาอยู่ เป็นโปรเจคจบปี 4 ของคณะไอทีลาดกระบัง

## คำอธิบายและภาพรวม
เป็นแอปพลิเคชันนำทาง โดยใช้กล้องบนสมาร์ทโฟนแอนดรอย ส่องไปยังจุดต่างๆ เพื่อหาภาพมาร์กเกอร์ที่ตรงกับรูปในฐานข้อมูล เมื่อเจอตำแหน่งแล้วจะแสดงข้อมูลของจุดนั้นๆ ในรูปแบบ AR (หากไม่ได้อยู่ในระหว่างการนำทาง)
ผู้ใช้สามารถดูตำแหน่งและทิศทางการหันของตนเองได้จากแผนที่มุมบน และสามารถเลือกปลายทางเพื่อให้ระบบเริ่มการนำทางไปยังจุดที่ต้องการได้ เมื่อยู่ในระหว่างการนำทางและส่องไปยังมาร์กเกอร์ ระบบจะแสดงลูกศรนำทางชี้ไปยังจุดถัดไปเรื่อยๆ เมื่อถึงปลายทางจะแสกดงลูกศรสีเขียว

## การใช้แอพพลิเคชัน

//จะเป็นรูป รอซักพักนะ ยังไม่ว่างมาเพิ่มเลย T_T


## การนำเข้าแผนที่อาคารอื่นๆ
1. เริ่มจากต้องมีรูปของแผนที่มุมบนก่อน นำรูปนั้นใส่ใน plane ปรับขนาดให้เป็น 1000 x 1000
2. หลังจากนั้น ถ่ายรูปในอาคารตามจุดต่างๆ แก้ไขรูปให้เป็นไปตามต้องการ แล้วอัปโหลดเข้าเว็บ vuforia
3. ดาวน์โหลดฐานข้อมูลจาก vuforia เลือกเป็น unity
4. จากนั้นเข้าไปใน unity เพื่อ import custom package ที่ได้ดาวน์โหลดมา
5. เพิ่ม image target ของ vuforia เข้าไป ปรับตำแหน่งและทิศทางการหันให้ตรงกับควมเป็นจริง และกาำหนดโดนหข้างเคียงที่สามารถเดินจากจุดนั้นไปหาได้
6. เลือกรูปของตำแหน่งนั้นๆในฐานข้อมูลของ vuforia

## ฟีเจอร์ในอนาคต
- [ ] แก้ไขฐานข้อมูลให้ใน 1 จุด มีมาร์กเกอร์ได้มากกว่า 1 ภาพ เพื่อให้ตรวจจับตำแหน่งได้ดีขึ้น
- [ ] เสียงอัตโนมัติ ช่วยในการนำทาง
- [ ] สามารถนำเข้าข้อมูลจุดต่างๆผ่านไฟล์ .json (ไม่ต้องเชื่อมโหนดเอง)
- [ ] เว็บสำหรับช่วยในการนำเข้าข้อมูล และสร้างไฟล์ .json 