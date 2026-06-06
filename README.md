# Neon Relic

-------------
**Đây là dự án vibecode game HTML được đạt top 1 trong tập 1 series vibecode của LCNQ**.

Đây là bản chính thức của mình. Để lấy bản legacy (bài nộp chính thức), hãy tìm https://github.com/RandomGuy-VN/Neon-Relic-Legacy
Prompt Deepseek (sử dụng bản V4 Pro):
```
Bạn là một senior game developer, game designer, UI/UX designer và creative director. Hãy tạo một game **2D futuristic RPG** chất lượng cao, chạy độc lập trên web, không cần server, không cần cài package, chỉ dùng HTML + CSS + JavaScript thuần trong một file `index.html`.

Mục tiêu: tạo một game đủ ấn tượng để đem đi thi vibecode. Game phải có cảm giác hoàn thiện như một mini indie RPG, không phải demo sơ sài.

Tên game: **Neon Relic: Echoes of Astra**

Thể loại: 2D futuristic action RPG / top-down RPG / dungeon exploration.

Bối cảnh:
Năm 2479, nhân loại sống trong các thành phố nổi gọi là Astra Cities. Một nguồn năng lượng cổ đại tên **Neon Relic** bị đánh cắp, khiến hệ thống AI bảo vệ thành phố phát điên. Người chơi là một “Relic Runner” — chiến binh lai công nghệ được giao nhiệm vụ đi vào các khu vực nhiễu loạn, tiêu diệt drone, thu thập mảnh Relic, nâng cấp bản thân và đánh bại AI lõi trung tâm.

Phong cách:

* Futuristic RPG.
* Cyberpunk neon.
* Thành phố tương lai, tàn tích công nghệ, AI, drone, relic cổ đại.
* Không khí bí ẩn, đẹp, có chiều sâu.
* Visual phải nổi bật với glow, particle, UI glassmorphism, neon HUD.

Yêu cầu kỹ thuật bắt buộc:

1. Tạo toàn bộ game trong **một file HTML duy nhất** gồm HTML, CSS và JavaScript.
2. Không dùng thư viện ngoài, không CDN, không ảnh ngoài, không âm thanh ngoài.
3. Dùng `<canvas>` để render game.
4. Game phải chạy tốt trên trình duyệt desktop hiện đại.
5. Có responsive layout, canvas tự co giãn theo kích thước màn hình.
6. Không được để code giả, TODO, placeholder, hoặc tính năng mô tả nhưng không hoạt động.
7. Code phải sạch, có cấu trúc rõ ràng: game state, player, enemies, particles, input, collision, rendering, audio, UI, RPG system.
8. Phải có comment vừa đủ để dễ hiểu.

Gameplay cốt lõi:

* Người chơi điều khiển nhân vật trong bản đồ top-down 2D.
* Điều khiển:

  * WASD hoặc phím mũi tên để di chuyển.
  * Chuột trái hoặc J để đánh thường.
  * Chuột phải hoặc K để dùng skill.
  * Space để dash.
  * E để tương tác / nhặt vật phẩm / nói chuyện.
  * P để pause.
  * R để restart sau khi thua.
* Trên mobile hoặc màn hình cảm ứng:

  * Joystick ảo bên trái để di chuyển.
  * Nút Attack, Skill, Dash bên phải.
* Người chơi có:

  * HP
  * Energy
  * Level
  * EXP
  * Credits
  * Attack damage
  * Defense
  * Crit chance
  * Skill cooldown
* Có hệ thống lên cấp:

  * Giết enemy nhận EXP.
  * Đủ EXP thì lên level.
  * Khi lên level, người chơi được chọn 1 trong 3 nâng cấp ngẫu nhiên.
  * Ví dụ nâng cấp:

    * Tăng HP tối đa.
    * Tăng damage.
    * Giảm cooldown skill.
    * Dash xa hơn.
    * Tăng crit chance.
    * Hồi máu khi giết enemy.
    * Skill bắn thêm projectile.
* Có hệ thống loot:

  * Enemy có thể rơi credits, energy orb, health orb.
  * Có chest trên bản đồ.
  * Chest cho upgrade tạm thời hoặc credits.
* Có nhiệm vụ chính:

  * Thu thập 3 mảnh Neon Relic.
  * Mỗi mảnh được bảo vệ bởi một nhóm enemy hoặc mini-boss.
  * Khi đủ 3 mảnh, boss cuối xuất hiện.
  * Đánh bại boss cuối thì hiện màn hình Victory.

Combat:

* Đánh thường là slash hoặc energy blade theo hướng chuột / hướng di chuyển.
* Skill là projectile năng lượng hoặc shockwave.
* Skill tốn energy và có cooldown.
* Dash có iframe ngắn hoặc giảm sát thương trong thời gian dash.
* Enemy có thanh máu.
* Khi đánh trúng enemy:

  * Có hit flash.
  * Có particle.
  * Có floating damage number.
  * Có knockback nhẹ.
* Khi người chơi bị đánh:

  * Camera shake.
  * Flash đỏ nhẹ.
  * Mất combo hoặc giảm energy.
* Combat phải mượt, rõ ràng, có cảm giác “đã tay”.

Enemy:
Tạo ít nhất 4 loại enemy:

1. **Scout Drone**

   * Bay nhanh, máu thấp, lao tới gần người chơi.
2. **Laser Sentinel**

   * Đứng xa, bắn laser theo chu kỳ, có cảnh báo trước khi bắn.
3. **Shield Bot**

   * Chậm, trâu, áp sát và gây damage cao.
4. **Glitch Wisp**

   * Di chuyển zigzag, để lại vùng nhiễu làm chậm người chơi.

Boss cuối:
Tên boss: **Astra Core Prime**

* Boss có nhiều phase.
* Phase 1: bắn projectile vòng tròn.
* Phase 2: gọi drone phụ.
* Phase 3: tạo laser quét ngang/dọc bản đồ.
* Boss có thanh máu lớn ở trên màn hình.
* Khi boss chết, tạo vụ nổ particle lớn, slow motion ngắn, hiện Victory screen.

Map:

* Bản đồ top-down dạng arena / dungeon thành phố tương lai.
* Có tường, vật cản, cột năng lượng, nền grid neon, terminal, chest, relic shrine.
* Map không cần quá lớn nhưng phải có cảm giác khám phá.
* Có minimap đơn giản ở góc màn hình.
* Có các khu vực:

  * Central Plaza
  * Broken Lab
  * Neon Alley
  * Core Gate
* Người chơi không đi xuyên tường.
* Enemy cũng nên tránh hoặc bị chặn bởi vật cản đơn giản.

RPG UI:

* Màn hình title:

  * Tên game “Neon Relic: Echoes of Astra”
  * Tagline: “Awaken the relic. Rewrite the future.”
  * Nút Start
  * Nút Sound On/Off
  * Nút How To Play
* HUD trong game:

  * HP bar
  * Energy bar
  * EXP bar
  * Level
  * Credits
  * Objective hiện tại
  * Minimap
  * Skill cooldown
  * Dash cooldown
* Pause menu:

  * Resume
  * Restart
  * Sound toggle
* Level up overlay:

  * Hiển thị 3 thẻ upgrade.
  * Người chơi chọn bằng chuột hoặc phím 1/2/3.
* Game over screen:

  * Level đạt được
  * Enemy đã tiêu diệt
  * Relic collected
  * Credits
  * High score lưu bằng `localStorage`
  * Nút Restart
* Victory screen:

  * Thời gian hoàn thành
  * Level cuối
  * Boss defeated
  * Rank đánh giá: C, B, A, S tùy thành tích.

Game feel và polish:

* Movement phải mượt, có acceleration/deceleration nhẹ.
* Dash phải có trail, cooldown rõ ràng.
* Camera có easing, không giật.
* Có camera shake khi hit, boss attack, relic collected.
* Có parallax background dạng thành phố neon / starfield / grid.
* Có glow effect giả lập bằng canvas shadowBlur.
* Có particle system cho:

  * trail người chơi,
  * slash attack,
  * projectile,
  * enemy death,
  * relic collected,
  * level up,
  * boss explosion,
  * background neon rain.
* Có floating text:

  * damage number,
  * critical hit,
  * EXP,
  * credits,
  * level up,
  * relic acquired.
* Có procedural sound bằng Web Audio API:

  * click menu,
  * slash,
  * skill,
  * dash,
  * hit enemy,
  * player hit,
  * enemy death,
  * level up,
  * relic collected,
  * boss warning,
  * victory,
  * game over.
* Thêm nút bật/tắt âm thanh.
* Không dùng file âm thanh ngoài.
* Có nhạc nền procedural đơn giản bằng oscillator/pads nếu có thể, nhưng phải có toggle và không gây khó chịu.

Visual style:

* Futuristic RPG cyberpunk.
* Nền tối xanh đen/tím đen.
* Glow neon xanh cyan, tím, hồng, cam.
* Player là nhân vật nhỏ có áo choàng năng lượng hoặc giáp tương lai.
* Vũ khí là energy blade.
* Relic là vật thể cổ đại phát sáng.
* Enemy drone/bot có mắt đỏ, shield, laser.
* Boss là lõi AI lớn với vòng tròn năng lượng.
* UI phải đẹp, hiện đại, giống game sci-fi:

  * glass panel,
  * gradient border,
  * neon glow,
  * animation hover cho button,
  * font system đẹp, không cần tải font ngoài.

Yêu cầu cân bằng:

* Game phải dễ hiểu trong 10 giây đầu.
* Enemy đầu game không quá khó.
* Người chơi phải cảm thấy mạnh dần qua upgrade.
* Skill phải hữu ích nhưng không spam vô hạn.
* Dash phải quan trọng để né laser/boss attack.
* Boss phải khó hơn enemy thường nhưng vẫn công bằng.
* Hitbox phải hợp lý, không gây cảm giác “bị đánh oan”.

Yêu cầu về code:

* Dùng class hoặc object rõ ràng cho:

  * Game
  * Player
  * Enemy
  * Boss
  * Projectile
  * Particle
  * FloatingText
  * Item
  * Chest
  * Obstacle
  * Relic
  * UpgradeCard
* Tách các hàm:

  * init()
  * startGame()
  * restartGame()
  * update(dt)
  * render()
  * updateInput()
  * updateCamera()
  * spawnEnemy()
  * spawnBoss()
  * spawnLoot()
  * checkCollisions()
  * applyUpgrade()
  * drawBackground()
  * drawWorld()
  * drawHUD()
  * drawMinimap()
  * playSound(type)
* Dùng helper functions:

  * clamp()
  * lerp()
  * dist()
  * angleTo()
  * randomRange()
  * circleRectCollision()
  * circleCircleCollision()
* Không để lỗi console.
* Không dùng alert.
* Không dùng prompt browser.
* Có xử lý resize canvas đúng cách.
* Có fallback khi Web Audio chưa được bật trước tương tác người dùng.

Yêu cầu đầu ra:

* Trả về **toàn bộ code hoàn chỉnh** trong một block duy nhất.
* File phải chạy ngay khi lưu thành `index.html` và mở bằng trình duyệt.
* Không giải thích dài dòng bên ngoài code.
* Không cắt bớt code.
* Không nói “phần còn lại tương tự”.
* Không dùng asset ngoài.
* Ưu tiên cảm giác chơi, độ mượt, polish, UI đẹp, hệ thống RPG rõ ràng và tính hoàn thiện.

Trước khi đưa code cuối cùng, hãy tự kiểm tra:

1. Start game có hoạt động không?
2. Player có di chuyển, attack, skill, dash được không?
3. Enemy có spawn, đuổi/bắn/đánh đúng không?
4. EXP, level up, upgrade card có hoạt động không?
5. Loot/chest/relic có hoạt động không?
6. Boss cuối có spawn và có phase không?
7. Game over, victory, restart, pause có hoạt động không?
8. Sound toggle có hoạt động không?
9. Minimap và HUD có hiển thị đúng không?
10. Canvas resize có vỡ layout không?
11. Có lỗi biến undefined nào không?
12. Game có đủ đẹp, đủ vui, đủ polish để gây ấn tượng trong cuộc thi không?

Bây giờ hãy tạo file `index.html` hoàn chỉnh.

```
Extra prompt (recommend nếu muốn làm tốt hơn):
```
Hãy tự đóng vai ban giám khảo cuộc thi vibecode, chấm game này theo gameplay, visual, polish, code quality và độ hoàn thiện. Sau đó nâng cấp trực tiếp code để tăng cơ hội thắng giải, ưu tiên thêm juice, RPG depth, boss fight, UI đẹp và giảm bug.
```
Prompt Suno (Toàn bộ đều ở Simple Mode + Instrumental)
Opening: 
```
Future bass and electronic rock anime opening at 174 BPM with four-on-the-floor drive, syncopated drums, palm-muted guitar chops, pulsing arpeggios, and a distorted synth lead carrying the main theme; intro glitches into a huge drop, verse stays lean and propulsive, pre-chorus swells with snare rolls and filters, final lift adds layered leads, gang-stab accents, and a halftime guitar break, Bright punchy mix, euphoric and cinematic, uplifting, glitch, electric, theme, rock, anime, electronic, soaring, bright
```
Ending:
```
Synthwave ballad with dream pop and ambient electronic foundation at 84 BPM, swung slow-drip pulse and brushed drums; intro opens on solo piano with room reverb and tape hiss, verse adds warm analog pads and soft sub bass, chorus swells with reverb-heavy electric guitar lead and layered strings pad, bridge strips back to piano and a single held tone, final chorus blooms then dissolves into an aching outro, Intimate, cinematic, lo-fi tape warmth, faded neon glow, warm, electronic, light, soft, lo-fi, emotional, nostalgic, electric, ambient, theme, slow, dream pop, ballad, gentle, anime
```
Bossfight:
```
Dark synthwave and drum and bass at 160 BPM with aggressive distorted bass, fast breakbeat drums, ominous choir pads, and screaming synth leads; intro stalks with low pulse and distant metallic hits, midsection drives harder with snare rushes and alarm stabs, break strips to sub rumble and filtered menace, final pass slams full force for a seamless loop, Cinematic, relentless, sharp, and विशाल with glossy grit, breakbeat, theme, drum and bass, electronic
```
