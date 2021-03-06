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


#### HomeWork 4 OBJ loader, drive, collision [網址連結](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/hw4.htm)
- 說明：載入一車子模型，在場景上藉由鍵盤控制車輛移動，場景中有大大小小的障礙物，當車子碰到障礙物時，要使車輛立即停止
- 開車: [Helper](https://docs.google.com/presentation/d/1dkUZC6EzHXr9WJ_oqd0d9RqcIMzdXeOQoyIGgqwxP80/edit)
- 載入模型: 利用合適的loader將其匯入three.js 場景中，以適當大小呈現
- 碰撞偵測：實作[此頁程式](https://docs.google.com/presentation/d/1vevW4pg9LDJlxUDB-xDjUM1k9Hfu4NXv9s1r3UC3ygQ/edit)，使得車輛與障礙物相撞時立即停止。使用者須自行將車輛駛出。
- 視野：螢幕分割成左右兩viewports,  一邊為上帝視角 (god's eye view), 一邊為駕駛的第三人稱視角 (third person view)
- 障礙物設計：可以用threejs所提供的geometry, 或是使用circular billboard (with cut-out texture)


#### HomeWork 5 Class, Raycaster, Shadow Map [網址連結](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/hw5.htm)
- 說明：在場景中放置桌子、檯燈、遙控器、椅子等物體，並實作遙控器按鈕Class和光影操作
- 遙控器：需有兩按鈕（以Class實作 [參考此處](https://jsfiddle.net/georgeChen/qgwb169w/)），一個操作檯燈的燈光，另一個操作室內燈光
- 光影：場景內的燈光和物件皆需做[Shadow Map](https://sites.google.com/site/cgwith3js/home/shadowmap)
- 進階要求：以 [PD Control](https://docs.google.com/presentation/d/1YwlfYz3jYuo8qjrgduSGvE5uNL0BIOf6aOBE8nMUpSY/edit)實作燈光之light up/dim out effect

#### HomeWork 6 First GLSL Shader homework [網址連結](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/hw6.htm)
- 說明：分成以下三大部分
- 1.Basic GLSL example: coordinate vs shading (with select/option)
  - 將上課示範的程式整合成一個html：利用select/option tags選擇`座標系統的種類(object/world/eye coordinate system)`以及`shading的方式(per-vertex/per-pixel)`.
  - 了解並整合程式碼，以達成所要的結果(+x white, -x black)。
  - 以[Utah teapot](https://en.wikipedia.org/wiki/Utah_teapot) 當成本作業的物件。
  - 場景中，在原點放置MeshPhongShaded的茶壺。另有一個同樣大小的茶壺，繞著原點公轉，以 shaders完成成像(shading) 
- 2.Gooch Shaded Teapot
  - 參考Gooch shading reference ([1](https://lva.cg.tuwien.ac.at/ecg/wiki/doku.php?id=students:gooch) , [2](http://artis.imag.fr/~Cyril.Soler/DEA/NonPhotoRealisticRendering/Papers/p447-gooch.pdf))， 只做shading的部分 （不用做 silhouette）。
  - Shader需接收light的world coordinate (uniform variable).
  - Point light以某個高度的圓形軌道運行。
- 3.Using GLSL shaders in a class
  - 將Gooch shaded teapotl 結合 class， 其重要屬性 life (生命值）簡述如下：
  - 每個茶壺有一定的生命值，隨著生命值的減少，自轉速度會降低，透明度會增加。當生命值為零時，不再旋轉，並在一 定時間內消失（從scene當中移除）
  - 茶壺初始時，以滑鼠，透過raycaster，放置在地面任意處，開始以localY軸自轉 
  - 若滑鼠點到已存在的茶壺，則toggle自轉。自轉停止時，生命值不變。
  - 在螢幕上顯示場景(scene)中仍有多少茶壺(以確定scene remove children成功)。
- Helpers：[HW6Demo](http://web.cse.ttu.edu.tw/jmchen/cg/fall17/hw6demo.html)、[transparent shaderMaterial](http://jsfiddle.net/jmcjc5u/8jhxmwbp/)、[placer](http://jsfiddle.net/game3js/116bxzve/)

