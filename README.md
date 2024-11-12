# Earth-Protector
@namespace
class SpriteKind:
    garbage1 = SpriteKind.create()
    bin2 = SpriteKind.create()
    gaebage2 = SpriteKind.create()
    garbage3 = SpriteKind.create()
    garbage4 = SpriteKind.create()
    bin1 = SpriteKind.create()
    bin3 = SpriteKind.create()
    bin4 = SpriteKind.create()
    bin22 = SpriteKind.create()

def on_on_overlap(sprite6, otherSprite6):
    mySprite8.set_flag(SpriteFlag.INVISIBLE, True)
    info.set_score(25)
sprites.on_overlap(SpriteKind.garbage3, SpriteKind.bin3, on_on_overlap)

def on_on_overlap2(sprite, otherSprite):
    mySprite6.follow(mySprite)
sprites.on_overlap(SpriteKind.player, SpriteKind.garbage1, on_on_overlap2)

def on_on_overlap3(sprite4, otherSprite4):
    mySprite9.set_flag(SpriteFlag.INVISIBLE, True)
    info.set_score(25)
sprites.on_overlap(SpriteKind.garbage4, SpriteKind.bin4, on_on_overlap3)

def on_a_pressed():
    global mySprite2, mySprite3, mySprite4, mySprite5, mySprite6, mySprite7, mySprite8, mySprite9
    scene.set_background_image(assets.image("""
        myImage6
    """))
    mySprite2 = sprites.create(assets.image("""
            Recycling waste bin
        """),
        SpriteKind.bin4)
    mySprite2.set_position(10, 10)
    mySprite3 = sprites.create(assets.image("""
        Food waste bin
    """), SpriteKind.bin3)
    mySprite3.set_position(10, 110)
    mySprite4 = sprites.create(assets.image("""
        Toxic waste Bin
    """), SpriteKind.bin1)
    mySprite4.set_position(150, 10)
    mySprite5 = sprites.create(assets.image("""
        Other waste bin
    """), SpriteKind.bin22)
    mySprite5.set_position(150, 110)
    mySprite6 = sprites.create(assets.image("""
        Toxic waste
    """), SpriteKind.garbage1)
    mySprite6.set_position(randint(20, 140), randint(20, 100))
    mySprite7 = sprites.create(assets.image("""
        Other waste
    """), SpriteKind.gaebage2)
    mySprite7.set_position(randint(20, 140), randint(20, 100))
    mySprite8 = sprites.create(assets.image("""
        Food waste
    """), SpriteKind.garbage3)
    mySprite8.set_position(randint(20, 140), randint(20, 100))
    mySprite9 = sprites.create(assets.image("""
            Recycling waste
        """),
        SpriteKind.garbage4)
    mySprite9.set_position(randint(20, 140), randint(20, 100))
controller.A.on_event(ControllerButtonEvent.PRESSED, on_a_pressed)

def on_on_score():
    game.game_over(True)
info.on_score(100, on_on_score)

def on_on_overlap4(sprite5, otherSprite5):
    mySprite6.set_flag(SpriteFlag.INVISIBLE, True)
    info.set_score(25)
sprites.on_overlap(SpriteKind.garbage1, SpriteKind.bin1, on_on_overlap4)

def on_on_overlap5(sprite2, otherSprite2):
    mySprite7.set_flag(SpriteFlag.INVISIBLE, True)
    info.set_score(25)
sprites.on_overlap(SpriteKind.gaebage2, SpriteKind.bin2, on_on_overlap5)

def on_on_overlap6(sprite3, otherSprite3):
    mySprite9.follow(mySprite)
sprites.on_overlap(SpriteKind.player, SpriteKind.garbage4, on_on_overlap6)

def on_on_overlap7(sprite7, otherSprite7):
    mySprite7.follow(mySprite)
sprites.on_overlap(SpriteKind.player, SpriteKind.gaebage2, on_on_overlap7)

def on_on_overlap8(sprite8, otherSprite8):
    mySprite8.follow(mySprite)
sprites.on_overlap(SpriteKind.player, SpriteKind.garbage3, on_on_overlap8)

mySprite7: Sprite = None
mySprite5: Sprite = None
mySprite4: Sprite = None
mySprite3: Sprite = None
mySprite2: Sprite = None
mySprite9: Sprite = None
mySprite6: Sprite = None
mySprite8: Sprite = None
mySprite: Sprite = None
scene.set_background_image(assets.image("""
    myImage7
"""))
mySprite = sprites.create(img("""
        . . . . . . 5 . 5 . . . . . . . 
            . . . . . f 5 5 5 f f . . . . . 
            . . . . f 1 5 2 5 1 6 f . . . . 
            . . . f 1 6 6 6 6 6 1 6 f . . . 
            . . . f 6 6 f f f f 6 1 f . . . 
            . . . f 6 f f d d f f 6 f . . . 
            . . f 6 f d f d d f d f 6 f . . 
            . . f 6 f d 3 d d 3 d f 6 f . . 
            . . f 6 6 f d d d d f 6 6 f . . 
            . f 6 6 f 7 f f f f 7 f 6 6 f . 
            . . f f d 7 5 7 7 5 7 d f f . . 
            . . f d d f 7 5 5 7 f d d f . . 
            . . . f f 7 7 7 7 7 7 f f . . . 
            . . . f 7 7 5 7 7 5 7 7 f . . . 
            . . . f f f f f f f f f f . . . 
            . . . . . f f . . f f . . . . .
    """),
    SpriteKind.player)
controller.move_sprite(mySprite, 100, 100)
mySprite.set_stay_in_screen(True)
effects.hearts.start_screen_effect(1000)
