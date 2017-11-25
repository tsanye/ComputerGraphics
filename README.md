# Computer Graphics 計算機圖學 上課作品集

課程概述與目標：computer graphics: principles and practices  webgl (three.js) & glsl shaders 


#### HomeWork 1 Time-based animation [網址連結](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/hw1.htm)
- 說明：創建一指針與背板於XY平面, 指針初始在正Y軸方向。碼錶依Real-time順時針旋轉, 使用於60秒內之計時。
- 功能：按下`Toggle Turn`後指針開始依順時針旋轉，再次按下時則是暫停。
- 美觀：不同display style：扇形。 並為碼錶貼上圖片：[背板](https://i.imgur.com/Q1NeB5J.png)、[指針](https://i.imgur.com/QpvBr1S.png)
- 運動：連續或是[Quartz Style](https://www.youtube.com/watch?v=zBflo3UG6Og)


#### HomeWork 2 Git & Github [網址連結](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/hw2-0.htm)
- 說明：將課堂作業的資料夾建成Repository並建立index.html，為本學期作業做一個title page，並上傳到github上
- 進階要求：參考[Markdown files的格式](https://help.github.com/articles/basic-writing-and-formatting-syntax/)，為homework repository加上合適的README.md 


#### HomeWork 3 Hierarchical model [網址連結](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/hw3.htm)
- 說明：坦克在中線(x = 0)上前後運動，地圖的兩端(x = 100, x = -100)隨機產生標靶。需操作坦克發射砲彈，將標靶擊落。
- 坦克：正確的機構(kinematic)[模型](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/tank.html)，以及合理的`joint angle limits`
- 砲彈：初始位置：砲口 發射方向：砲管方向; 發射速率：固定。砲彈打到地面(y=0)即停止。之後才可以發射下一發砲彈。
- 視野：god's eye view 以及 坦克操作員視角（方便瞄準）
- 美觀：為場景和坦克模型架設合適的燈光，設定合適的顏色
- 進階要求：[參考](https://docs.google.com/presentation/d/17tTiIvHCruuUXcSnboq1dPTnf0tQtg53xqUdj3nE2zw/edit#slide=id.p)此處，將砲彈創建成Class , 使坦克可以發射多發。