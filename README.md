# RPG--Harry Potter
## 故事主線:
- Welcome to the Wizarding world! The world is in Voldemort's control...
  Everyone live in desperate and wish a Savior to protect them.
  As a descendent of Lily and James Poter, can you try your best to save the world?
  You should try to beat all the Death Eater or collect the 7 hallows, which are Voldemort's Horcrux(分靈體)
  ![image](https://github.com/tyynmk25/tyynmk25/blob/main/1.jpg)
## 故事開場：
- Sorting Hat : Hmmm...Difficult to sort...Plenty of courage and kind heart...
- Harry Potter: Not Slytherin!
- Sorting Hat: Are you sure? You will get great success there. But if not Slytherin...Gryffindor!
## 遊戲規則簡介
  You are going to collect all the hollows to beat the Voldemort.
  To collect the hollows, you will have to walk through the field, and beat the monsters you encounter.
  There are 5 hollows now in this field, and the other two are in another 2 fields.
  Once you collect 5 hollows and step on the square that is marked with W, you will be sent to another field.
  Besides monster, you may go to a store, encounter some special activities that is marked with @@
  After a battle, you can save your game status to a save.txt
  Your journey starts!
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/2.jpg)
## 角色設定：
- 為自己的角色設定名字
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/3.jpg)
- 顯示隊友Ron, Hermione 的資訊
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/4.jpg)
### 選擇要用初始化的角色還是要load file 裡的角色( 輸入1為load file, 其他則為初始化角色) 
#### 輸入1 :
- 從檔案讀出角色的資料，放入player_list[0]
- 從檔案讀到玩家現在在哪張地圖的哪個位置
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/5.jpg)
#### 輸入其他：
- 初始化角色，且由map1 (1,1)開始走
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/7.jpg)
##### 實作方法
- 使用unserialize()讀檔做出角色
- 使用readmap()和loadmap()讀出現在的地圖和座標位置
## 遊戲開始：
### 在地圖上走迷宮，用WASD控制方向
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/6.jpg)
### 被渾拚柳吹到隨機的地方(@@)
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/11.jpg)
### 抽獎(@@)
- 除了咒語是1/60機率，其他皆有機會中獎，如果重量或數量不合導致無法放入，輸出"Can't put"-
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/12.jpg)
### 猜數字(@@)
- 如果猜對會獲得寶劍
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/13.jpg)
### 塔羅牌算命(@@)
- 命運會隨機決定，可能會扣錢或得到錢，也可能增加經驗值...等等
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/14.jpg)
### Hint(@@)
- 告訴玩家最後一個聖物的所在地
### 得到地圖2(WW)
- 如果已經獲得五個聖物，則踩到此格可以直接被送往地圖2，否則繼續在地圖1蒐集聖物
### 得到地圖3(WW)
- 如果已經獲得六個聖物，則踩到此格可以直接被送往地圖3，否則繼續在地圖2蒐集聖物
### 如果收集完7個聖物，且踩到此格，遊戲結束，玩家獲勝

### 遇到商店：
#### 問玩家是否要前往商店(y=yes, n=no)
##### 若為yes
- 1. sword(weaponitem): $20// requierd level=1 
- 2. wand(weaponitem): $30// required level=3 
- 3. cloak(armoritem): $50// required level=3
- 4. protector(armouritem): $80//required level=5
- 5. lifepotion(consumableitem): $100//required level=5
- 6. killing(consumableitem): $150//required level=8
##### 請玩家輸入要買哪個道具
- Press a to buy a sword, b to buy a wand, c to buy a cloak,d to buy a protector, e to buy a lifepotion,f to buy a killing curse.Press x to leave
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/9.jpg)
### 遇到戰鬥：
#### 在戰鬥之前
- 1. 在戰鬥前，如果玩家背包有道具則詢問玩家是否要使用道具
- (Battle is going to start, would you like to change your equipment?)
- 2. 如果背包沒有道具，直接開始戰鬥
##### 若要使用道具，則秀出背包所有道具，請玩家輸入要放入的編號
- ![image](https://github.com/tyynmk25/tyynmk25/blob/main/10.jpg)
##### 若背包有consumable 的道具，請玩家輸入是否要使用
##### 實作方法
- 1. 先去檢查backpack，如果第一格!=NULL，則開始輸出backpack每一格的道具
- 2. 如果有consumable，則問玩家要不要使用
#### 開始戰鬥
##### 實作方法
- 1. 每一個battle都有不同種怪物、不同數量組成，actionlist先把玩家(共3人)放入，再放入Monster
- 2. 輪到玩家攻擊時，從Monster第一個開始找，若alive==1則先攻擊他，monster攻擊時則是從第三位玩家開始進行攻擊
- 3. 用for和while迴圈讓他們進行戰鬥
- 4. 直到有一方全部死掉(hp==0)，則戰鬥結束，若玩家獲勝則獲得一個hollow和Money、經驗值...等
- 5. 戰鬥結束後會問完加是否要save file，把遊戲status 輸出成save.txt
- 6. 這一格在戰鬥結束後會被設為空地
<!---
tyynmk25/tyynmk25 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
