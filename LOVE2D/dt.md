**📌 What is `dt` (Delta Time)?**  
🔹 `dt` is the **time elapsed between two frames** in seconds.  
🔹 LOVE2D **runs at variable FPS** (frames per second). If your computer is fast, frames come quickly (small `dt`). If it's slow, frames take longer (large `dt`).  
🔹 Using `dt` ensures movement is **consistent across different computers**.  

---

### **📌 Understanding `dt` with Printing**
Modify `love.update(dt)` to print `dt`:  
```lua
function love.update(dt)
    print("Delta Time:", dt) -- Print dt in console
    Player.move(dt)
end
```
📌 **Run your game and check the console output**  

🔹 **Expected Output (Values will vary)**  
```
Delta Time: 0.016
Delta Time: 0.017
Delta Time: 0.015
Delta Time: 0.016
...
```
⏳ **Why does `dt` keep changing?**  
Your FPS (frames per second) isn’t always **exactly** 60. So `dt` varies slightly!  

---

### **📌 How `dt` Affects Movement?**
💡 **Example:**  
If you set **speed = 200**, then in **one second**, the player moves **200 pixels**.  
- At **60 FPS** (`dt ≈ 1/60 = 0.016` sec),  
  `Player.x = Player.x + 200 * 0.016` → Moves **3.2 pixels per frame**.  
- At **30 FPS** (`dt ≈ 1/30 = 0.033` sec),  
  `Player.x = Player.x + 200 * 0.033` → Moves **6.6 pixels per frame**.  

✅ Since we multiply by `dt`, **the movement stays consistent regardless of FPS**. 🎯  

---

## **✅ Conclusion**
1️⃣ If `dt` is small (high FPS), movement **per frame is less**, so motion is smooth.  
2️⃣ If `dt` is large (low FPS), movement **per frame is more**, preventing lag.  
3️⃣ Without `dt`, movement would **depend on FPS**, making it **unfair** on different devices.  
