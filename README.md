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
- ![image] (https://github.com/tyynmk25/tyynmk25/blob/main/2.jpg)
## 遊戲規則簡介
  You are going to collect all the hollows to beat the Voldemort.
	To collect the hollows, you will have to walk through the field, and beat the monsters you encounter.
	There are 5 hollows now in this field, and the other two are in another 2 fields.
	Once you collect 5 hollows and step on the square that is marked with W, you will be sent to another field.
	Besides monster, you may go to a store, encounter some special activities that is marked with @@
	After a battle, you can save your game status to a save.txt
	Your journey starts!
## 角色設定：
- 為自己的角色設定名字
- 顯示隊友Ron, Hermione 的資訊
- ![image]  (https://github.com/tyynmk25/tyynmk25/blob/main/3.jpg)
### 選擇要用初始化的角色還是要load file 裡的角色( 輸入1為load file, 其他則為初始化角色) 
#### 輸入1 :
- ![image]  (https://github.com/tyynmk25/tyynmk25/blob/main/4.jpg)
#### 輸入其他 ：

## 遊戲開始：
### 在地圖上走迷宮，用WASD控制方向
### 遇到事件:
- 1. 例如: Oops!!You are attack by the Whomping Willow(渾拚柳)!You are thrown to a random place on the map!
   - 1.1 會將玩家的位置隨機放到地圖上的任何一個地方
### 遇到商店:Welcome to Honey's Duke!
#### 如果有錢的話可以選擇購買道具: sword, wand, cloak, protector, lifepotion, killing curse
#### 如果背包有位置(slot符合) 、重量符合(<=backpack_weight_limit) 就可以購買
#### 道具有以下幾種
##### Press a to buy a sword, b to buy a wand, c to buy a cloak,d to buy a protector, e to buy a lifepotion,f to buy a killing curse.
##### Press x to leave
- 1. sword(weaponitem): $20// requierd level=1 
- 2. wand(weaponitem): $30// required level=3 
- 3. cloak(armoritem): $50// required level=3
- 4. protector(armouritem): $80//required level=5
- 5. lifepotion(consumableitem): $100//required level=5
- 6. killing(consumableitem): $150//required level=8

### 遇到戰鬥：
#### 在戰鬥之前
- 1. 在戰鬥前，如果玩家背包有道具則詢問玩家是否要使用道具
- (Battle is going to start, would you like to change your equipment?)
##### 如果要使用: 顯示背包裡的道具
- 開始問玩家要使用背包的第幾號道具將他裝備在身上
##### 道具配置：
- Press the number of the item you want to equip, or input x to leave
- 檢查輸入的號碼對應到背包裡的哪一個道具，將他配置於weapon 或 armor
##### 如果要使用 但背包裡沒有道具:
- Oops!Your backpack is empty.
- 前往戰鬥 戰鬥開始

##### 道具配置完畢，則開始戰鬥
#### 戰鬥開始:
##### 如果背包裡有consumable item 則問玩家是否要使用
##### 如果玩家有配置weapon 和 armor 
- 把weapon 和armor 各自的功效(提升攻擊力或防禦力等) 在戰鬥前先提升
##### 如果玩家打贏怪物，則獲得money +20
### 走到終點
- 遊戲結束 


<!---
tyynmk25/tyynmk25 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
