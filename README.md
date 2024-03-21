## Clothes-Flipper-Robot

#ณปพน วงค์คม 650610834

code สำหรับจำลองหุ่นยนต์พับผ้า ที่มี 6 degree of freedom
ทุกไฟล์จะอยู่ใน src/articubot_one/
- config:
    - controllers.yaml ใช้สำหรับกำหนด parameter สำหรับ publish ไปยัง topic ของ ros2 ใน repo นี้ topic ที่ใช้ตือ arm_controller parameter ของ joint: arm_1_joint,arm_2_joint,arm_3_joint,arm_4_joint,arm_5_joint,grip_1_joint,grip_2_joint คือ position
- description: จะรวมไฟล์ที่สำคัญทุกอย่างไว้ เช่น
    - model.dae 
    - robot_core.xacro ที่เป็นแกนหลักของการจำลองหุ่น ใช้ปรับ joint,model และ inertial ของหุ่นยนต์
    - file_transmission.xacro ที่่ทำให้สามารถควบคุม joint ด้วย plugin gazebo_ros2_control ได้
    - robot.urdf.xacro มีไว้รวม file.xacro ต่างๆไว้ แล้วเอาไปรันที่เดียว
    - inertial_macros.xacro มีไว้สำหรับคำนวนเพื่อสร้างกล่อง inertial ให้ model
    - gazebo_control.xacro มีไว้ส่ง joint ของล้อไปที่ odom เพื่อทำการควบคุมผ่าน keyboard
    - robot_control.urdf.xacro ทำให้ไฟ controllers.yaml สามารถใช้งาน plugin ได้
- launch:
    - launch_sim.launch.py ใช้สำหรับรันไฟล์ที่จำเป็นทุกอย่าง เพื่อให้ไฟล์ใช้งานได้ร่วมกัน
- worlds:
    เก็บ file.world ที่นำมารันใน launch_sim
- controller.py:
    ไฟล์ที่ใช้สำหรับการควบคุมด้วย keyboard
      
