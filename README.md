# Neon Relic

-------------
**Đây là dự án vibecode game HTML được đạt top 1 trong tập 1 series vibecode của LCNQ**
Phân loại: index.html: bản chính thức. index-legacy.html: bản legacy (bản dự thi)
Prompt Deepseek (sử dụng bản V4 Pro):
```
Bạn là một senior game developer, UI/UX designer và creative director. Hãy tạo một game 2D chất lượng cao, chạy độc lập trên web, không cần server, không cần cài package, chỉ dùng HTML + CSS + JavaScript thuần trong một file `index.html`.

Mục tiêu: tạo một game đủ ấn tượng để đem đi thi vibecode. Game phải có cảm giác hoàn thiện như mini indie game, không phải demo sơ sài.

Tên game: **Moonlit Courier**

Thể loại: 2D arcade action / delivery runner / survival.

Bối cảnh:
Người chơi là một shipper bay bằng hoverboard trong thành phố neon về đêm. Nhiệm vụ là giao các “moon packages” đến các điểm sáng trên bản đồ, né drone cảnh sát, biển quảng cáo rơi, tia laser, mưa sao băng và các vùng nhiễu điện. Càng giao nhiều đơn liên tiếp mà không bị va chạm thì combo càng cao.

Yêu cầu kỹ thuật bắt buộc:

1. Tạo toàn bộ game trong **một file HTML duy nhất** gồm HTML, CSS và JavaScript.
2. Không dùng thư viện ngoài, không CDN, không ảnh ngoài, không âm thanh ngoài.
3. Dùng `<canvas>` để render game.
4. Game phải chạy tốt trên trình duyệt desktop hiện đại.
5. Có responsive layout, canvas tự co giãn theo kích thước màn hình.
6. Không được để code giả, TODO, placeholder, hoặc tính năng mô tả nhưng không hoạt động.
7. Code phải sạch, có cấu trúc rõ ràng: game state, player, enemies, particles, input, collision, rendering, audio, UI.
8. Phải có comment vừa đủ để dễ hiểu.

Gameplay cốt lõi:

* Người chơi điều khiển nhân vật bay trong vùng chơi 2D nhìn từ trên xuống.
* Điều khiển:

  * WASD hoặc phím mũi tên để di chuyển.
  * Space để dash.
  * P để pause.
  * R để restart sau khi thua.
* Trên mobile hoặc màn hình cảm ứng:

  * Kéo ngón tay để di chuyển.
  * Double tap để dash.
* Người chơi có máu, năng lượng dash, điểm số, combo, thời gian sống sót.
* Package xuất hiện ở một điểm, destination xuất hiện ở điểm khác.
* Người chơi chạm vào package để nhặt, sau đó chạm vào destination để giao.
* Mỗi lần giao thành công:

  * Tăng điểm.
  * Tăng combo.
  * Tạo hiệu ứng particle đẹp.
  * Tăng độ khó một chút.
  * Có thể spawn thêm obstacle hoặc enemy.
* Nếu người chơi va chạm enemy/obstacle:

  * Mất máu.
  * Mất combo.
  * Có hiệu ứng rung màn hình, flash, particle.
* Khi máu về 0 thì game over.
* Có high score lưu bằng `localStorage`.

Game feel và polish:

* Movement phải mượt, có acceleration/deceleration nhẹ.
* Dash phải có trail, cooldown rõ ràng.
* Có camera shake khi va chạm hoặc giao hàng thành công.
* Có parallax background dạng thành phố neon, grid, sao, mây hoặc bảng hiệu.
* Có glow effect giả lập bằng canvas shadowBlur.
* Có particle system cho:

  * trail của người chơi,
  * vụ nổ nhỏ khi va chạm,
  * hiệu ứng giao hàng,
  * mưa neon nền.
* Có procedural sound bằng Web Audio API:

  * âm thanh nhặt package,
  * giao hàng,
  * dash,
  * hit,
  * game over,
  * click menu.
* Thêm nút bật/tắt âm thanh.
* Không dùng file âm thanh ngoài.

Visual style:

* Phong cách cyberpunk neon, màu nền tối, điểm sáng tím/xanh/cam.
* Player là một biểu tượng hoverboard hoặc courier nhỏ có glow.
* Package là khối sáng màu vàng.
* Destination là vòng tròn phát sáng.
* Enemy drone là hình tam giác/hexagon có mắt đỏ hoặc vòng scan.
* Obstacle có laser line, mine, billboard shard hoặc electric zone.
* UI phải đẹp, hiện đại:

  * title screen,
  * HUD trong game,
  * pause overlay,
  * game over screen,
  * high score,
  * hướng dẫn điều khiển ngắn gọn.
* Dùng CSS đẹp cho menu, button, typography, gradient, glassmorphism nhẹ.

Nội dung game cần có:

1. Màn hình title:

   * Tên game “Moonlit Courier”
   * Tagline ngắn, ví dụ: “Deliver light through a city that hunts you.”
   * Nút Start
   * Nút Sound On/Off
   * Hướng dẫn điều khiển
2. HUD:

   * Score
   * Combo
   * Health
   * Dash energy
   * Current objective: “Pick up package” hoặc “Deliver package”
   * High score
3. Game loop hoàn chỉnh:

   * update theo delta time
   * render theo requestAnimationFrame
   * xử lý pause/resume
4. Hệ thống độ khó:

   * Càng nhiều delivery, enemy càng nhanh.
   * Spawn thêm drone, laser, mine hoặc hazard.
   * Sau một số delivery nhất định, có “storm phase” ngắn: nhiều chướng ngại hơn, nền đổi màu, nhạc/âm thanh căng hơn.
5. Enemy behavior:

   * Drone chase người chơi nhưng không quá unfair.
   * Một số drone đi patrol ngang/dọc.
   * Laser hazard bật/tắt theo chu kỳ, có cảnh báo trước khi bật.
   * Mine đứng yên, phát sáng, nổ nếu người chơi lại gần.
6. Balance:

   * Game phải dễ hiểu trong 5 giây đầu.
   * Không quá khó ngay từ đầu.
   * Dash dùng để thoát nguy hiểm, có cooldown hợp lý.
   * Collision phải công bằng, có bán kính hợp lý.
7. Juice:

   * Combo text pop-up khi giao hàng.
   * Floating score text.
   * Background chuyển động nhẹ.
   * Screen shake vừa phải.
   * Slow flash ngắn khi hit.
   * Player trail khi dash.
   * Giao hàng thành công có vòng sóng lan ra.

Yêu cầu về chất lượng code:

* Dùng class hoặc object rõ ràng cho Player, Enemy, Particle, FloatingText, Hazard.
* Tách các hàm:

  * init()
  * startGame()
  * update(dt)
  * render()
  * updateInput()
  * spawnEnemy()
  * spawnHazard()
  * checkCollisions()
  * drawBackground()
  * drawHUD()
  * playSound(type)
* Dùng clamp, lerp, distance helper functions.
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
* Ưu tiên cảm giác chơi, độ mượt, polish, UI đẹp và tính hoàn thiện.

Trước khi đưa code cuối cùng, hãy tự kiểm tra:

1. Start game có hoạt động không?
2. Player có di chuyển và dash được không?
3. Package/destination có hoạt động đúng không?
4. Enemy/hazard có spawn và collision đúng không?
5. Game over/restart/high score có hoạt động không?
6. Pause có hoạt động không?
7. Sound toggle có hoạt động không?
8. Canvas resize có vỡ UI không?
9. Có lỗi biến undefined nào không?
10. Game có đủ đẹp và đủ vui để gây ấn tượng trong cuộc thi không?

Bây giờ hãy tạo file `index.html` hoàn chỉnh.
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
