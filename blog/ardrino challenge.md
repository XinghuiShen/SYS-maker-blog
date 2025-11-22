# Flag 3 Solution: Sensor to Actuator
# Flag 3 解决方案：传感器到执行器

**Student Name | 学生姓名**: _Yashu Shao________________

**Date Completed | 完成日期**: _11/29________________

---

## 📋 System Overview | 系统概述

### Project Name | 项目名称

auto-light

### Sensor-Actuator Pair | 传感器-执行器对

**Sensor Used | 使用的传感器**: 
ambient light sensor
**Actuator Used | 使用的执行器**: 
LED
---

### System Description | 系统描述

**What does your system do? Describe the interaction:**  
**你的系统做什么？描述交互：**

the light sensor detects light and open the LED when environmental light is low, and close when it feels light


**Real-world application | 实际应用**:  
*What problem could this solve or where could it be used?*  
*这可以解决什么问题或在哪里使用？*
use it outside so it opens at night automatically



---

## 🔌 Wiring | 接线

### Complete Pin Connections | 完整引脚连接

**Sensor Connections | 传感器连接**:

| Sensor Pin | Arduino Pin | 传感器引脚 | Arduino引脚 |
|------------|-------------|-----------|-------------|
| VCC | | VCC | |
| GND | | GND | |
| Signal/OUT | | 信号/OUT | |

**Actuator Connections | 执行器连接**:

| Actuator Pin | Arduino Pin | 执行器引脚 | Arduino引脚 |
|--------------|-------------|------------|-------------|
| VCC/+ | | VCC/+ | |
| GND/- | | GND/- | |
| Signal | | 信号 | |

**Additional Components | 额外组件**:
- [ ] Resistor (value: _______Ω)
- [ ] Other: __________

---

### Wiring Diagram/Photo | 接线图/照片

![Wiring Photo](./wiring.jpg)

*Or describe the complete circuit:*  
*或描述完整电路：*




---

## 💻 Code | 代码

### Complete Arduino Code | 完整Arduino代码

```cpp
// Paste your complete code here
// 在此粘贴完整代码
// Project - Auto Light  
int LED = 13;                    // Define LED pin as digital pin 13  
int val = 0;                      
// Define variable to store analog reading from pin 0 (light sensor)  
  
void setup(){  
     pinMode(LED, OUTPUT);        // Set the LED pin as OUTPUT mode  
     Serial.begin(9600);          
// Initialize serial communication with a baud rate of 9600  
}  
  
void loop(){  
     val = analogRead(0);         
// Read analog value from pin 0 (ranging from 0 to 1023)  
     Serial.println(val);         
// Print the analog value to the serial monitor  
     if(val < 1000){              
// If the analog value is less than 1000,  
          digitalWrite(LED, LOW); // turn the LED OFF  
     }else{                       // Otherwise,  
          digitalWrite(LED, HIGH);// turn the LED ON  
     }  
     delay(10);                   
// Wait for 10 milliseconds before the next loop iteration  
}  





```

---

### Code Structure Explanation | 代码结构解释

**Setup Section | 设置部分**:
void setup(){  
     pinMode(LED, OUTPUT);        // Set the LED pin as OUTPUT mode  
     Serial.begin(9600);          
// Initialize serial communication with a baud rate of 9600  



**Loop Section | 循环部分**:
void loop(){  
     val = analogRead(0);         
// Read analog value from pin 0 (ranging from 0 to 1023)  
     Serial.println(val);         
// Print the analog value to the serial monitor  
     if(val < 1000){              
// If the analog value is less than 1000,  
          digitalWrite(LED, LOW); // turn the LED OFF  
     }else{                       // Otherwise,  
          digitalWrite(LED, HIGH);// turn the LED ON  
     }  
     delay(10);                   
// Wait for 10 milliseconds before the next loop iteration  
}  



**Control Logic | 控制逻辑**:
- [ 1] Simple if/else (简单if/else)
- [ 1] Threshold-based (基于阈值)
- [ ] Proportional control with `map()` (使用map()的比例控制)
- [ ] Multiple conditions (多个条件)
- [ ] Other: __________

---

## 🎯 Interaction Logic | 交互逻辑

### Cause and Effect | 因果关系

**When sensor detects | 当传感器检测到**: 
light-LOW


**Then actuator does | 然后执行器做**: 
LED light up


---

### Conditions/Thresholds | 条件/阈值

**If using thresholds, list them here:**  
**如果使用阈值，在此列出：**

| Condition | Sensor Value Range | Actuator Response | 条件 | 传感器值范围 | 执行器响应 |
|-----------|-------------------|-------------------|------|-------------|-----------|
| | | | | | |
| | | | | | |
| | | | | | |

---

### Key Code Snippet | 关键代码片段

**The most important part of your logic:**  
**你的逻辑中最重要的部分：**

```cpp
// Paste the key section here
// 在此粘贴关键部分

void loop(){  
     val = analogRead(0);         
// Read analog value from pin 0 (ranging from 0 to 1023)  
     Serial.println(val);         
// Print the analog value to the serial monitor  
     if(val < 1000){              
// If the analog value is less than 1000,  
          digitalWrite(LED, LOW); // turn the LED OFF  
     }else{                       // Otherwise,  
          digitalWrite(LED, HIGH);// turn the LED ON  
     }  
     delay(10);                   
// Wait for 10 milliseconds before the next loop iteration  
}  
```

**Explanation | 解释**:
it detects the light in environment to see if it is near the limit



---

## 📊 Testing & Results | 测试和结果

### Testing Process | 测试过程

**How did you test your system?**  
**你如何测试系统？**

use a flash light to shine on the sensor


---

### Observed Behavior | 观察到的行为

**Test 1 | 测试1**:
- Sensor input: _light________________
- Actuator response: __LED off_______________
- Result: ☐1 As expected ☐ Unexpected

**Test 2 | 测试2**:
- SSensor input: _light________________
- Actuator response: __LED off_______________
- Result: ☐1 As expected ☐ Unexpected


**Test 3 | 测试3**:
-Sensor input: _light________________
- Actuator response: __LED off_______________
- Result: ☐1 As expected ☐ Unexpected

---

### Serial Monitor Output | 串口监视器输出

![Serial Output Screenshot](./serial-output.png)

*Or paste sample output:*  
*或粘贴示例输出：*

```
// Sample serial output
// 示例串口输出
1001
1001
1002
1001
1001
1001

```

---

## 📸 Demonstration | 演示

### Photo/Video | 照片/视频

**Upload photos or video showing your system in action**  
**上传显示系统运行的照片或视频**

![Demo 1](./demo1.jpg)
![Demo 2](./demo2.jpg)

**Video link** (if applicable): _________________

---

### Demonstration Description | 演示描述

**Describe what happens in your demo:**  
**描述演示中发生了什么：**

the LED is on at first but when I use a flah light on it. it's off


---

## 🎓 Reflection | 反思

### What Worked Well | 什么做得好
the hard ware and it worked



---

### Challenges Faced | 面临的挑战

**Technical challenges | 技术挑战**:
programming



**How you solved them | 你如何解决**:
use arduino web page as help



---

### What I Learned | 我学到的东西

**New concepts | 新概念**:
C language and arduino



**Key skills practiced | 练习的关键技能**:
- [ 1] Reading sensor data
- [ ] Controlling actuators
- [ 1] Conditional logic (if/else)
- [ 1] Value mapping
- [ ] Debugging interactive systems
- [ ] Other: __________

---

### Real-World Applications | 实际应用

**Where could this type of system be used?**  
**这类系统可以在哪里使用？**

street lights


**What improvements would make it production-ready?**  
**什么改进可以使其达到生产就绪？**

make sensor more accurate


---

## 🌟 Bonus Features (Optional) | 加分功能（可选）

**Did you add any extra features?**  
**你添加了任何额外功能吗？**




---

## ⏱️ Time Spent | 花费时间

**Total time | 总时间**: ___72____ minutes (分钟)

**Breakdown | 分解**:
- Planning: ___10__min (规划)
- Wiring: __25___min (接线)
- Coding: __22___min (编码)
- Testing/Debugging: __10___min (测试/调试)
- Documentation: ___5__min (文档)

---

## ✅ Verification | 验证

Check off before submitting:

提交前勾选：

- [ 1] Code compiles without errors (代码编译无错误)
- [1 ] Sensor correctly reads input (传感器正确读取输入)
- [1 ] Actuator responds to sensor changes (执行器响应传感器变化)
- [ 1] Cause-and-effect relationship is clear (因果关系清晰)
- [ 1] Code includes conditional logic (代码包含条件逻辑)
- [ 1] System is documented with photos/video (系统有照片/视频记录)
- [ 1] Serial Monitor output included (包含串口监视器输出)
- [ 1] All template sections filled out (所有模板部分都已填写)

---

## 🚀 Next Steps | 下一步

**Ideas for Flag 4 (Complex Logic):**  
**Flag 4（复杂逻辑）的想法：**

In Flag 4, you'll use multiple sensors and actuators. Based on this project:

在Flag 4中，你将使用多个传感器和执行器。基于这个项目：

**What additional sensors/actuators would enhance your system?**  
**哪些额外的传感器/执行器可以增强你的系统？**

temperature sensor


---

## 🎉 Congratulations! | 恭喜！

**You've captured Flag 3!** 🚩  
**你捕获了Flag 3！** 🚩

You now understand:
- How to create interactive systems (如何创建交互系统)
- Sensor-actuator integration (传感器-执行器集成)
- Conditional logic and control (条件逻辑和控制)
- Real-time system responses (实时系统响应)

**This is real embedded systems engineering! Ready for Flag 4?** 🚀  
**这是真实的嵌入式系统工程！准备好Flag 4了吗？** 🚀

---

**Date Submitted | 提交日期**: __11/29_______________

**Instructor Feedback | 讲师反馈**:

