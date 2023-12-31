# Npao
from kivy.app import App
from kivy.uix.widget import Widget
from kivy.uix.image import Image
from kivy.uix.behaviors import ButtonBehavior
from kivy.core.window import Window
from kivy.clock import Clock

class Character(ButtonBehavior, Image):
    def __init__(self, **kwargs):
        super(Character, self).__init__(**kwargs)
        self.source = 'character.png'  # Thay đổi 'character.png' bằng hình ảnh nhân vật của bạn
        self.size = (100, 100)
        self.pos = (Window.width / 2 - self.width / 2, Window.height / 2 - self.height / 2)

    def on_press(self):
        print("Character is moving!")

class GameApp(App):
    def build(self):
        return Character()

if __name__ == '__main__':
    GameApp().run()
