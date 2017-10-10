# Architecture ShipDemo
# (Lab1 GDX)

Berikut perkiraan kami dari arsitektur game ShipDemo:

| Model | View | Controller |
| ------ | ------ | ------ |
| Ship | GameCanvas | ModeController |
| PhotonQueue | GDXRoot | CollisionController |
| FilmStrip | | GameMode |
|  |  | LoadingMode |
|  |  | InputController |
|  |  | Xbox360Controller |

## Model
* Ship

  Class model yang mewakili ship  
  
* PhotonQueue

  Class model yang mewakili sistem partikel dari photon yang ditembakkan ship
  
* FilmStrip

  Texture class yang menyediakan animasi flipbook

## View
* GameCanvas

  Class view utama untuk permainannya, abstrak panggilan dasar grafis
  
* GDXRoot

  Root class dari LibGDX
  
## Controller
* ModeController

  Interface untuk kelas root dari player mode

* CollisionController

  Controller yang menerapkan physics sederhana
  
* GameMode

  Class controller utama dari game
  
* LoadingMode

  Class yang menyediakan layar loading untuk state dari game
  
* InputController

  Class untuk manager input
  
* Xbox360Controller

  Class untuk mendukung XBox 360 controller

  
