# basic-Tarot-card-reading
This script includes a deck of Tarot cards and a function to draw a specified number of cards for a reading.
import random

class TarotCard:
    def __init__(self, name, meaning):
        self.name = name
        self.meaning = meaning

    def __str__(self):
        return f'{self.name}: {self.meaning}'

class TarotDeck:
    def __init__(self):
        self.cards = [
            TarotCard("The Fool", "New beginnings, optimism, trust in life"),
            TarotCard("The Magician", "Action, the power to manifest"),
            TarotCard("The High Priestess", "Inaction, going within, the subconscious"),
            TarotCard("The Empress", "Abundance, nurturing, fertility, life in bloom!"),
            TarotCard("The Emperor", "Structure, stability, rules and power"),
            TarotCard("The Hierophant", "Institutions, tradition, society and its rules"),
            TarotCard("The Lovers", "Sexuality, passion, choice, uniting"),
            TarotCard("The Chariot", "Movement, progress, integration"),
            TarotCard("Strength", "Courage, subtle power, integration of animal self"),
            TarotCard("The Hermit", "Meditation, solitude, consciousness"),
            TarotCard("Wheel of Fortune", "Cycles, change, ups and downs"),
            TarotCard("Justice", "Fairness, equality, balance"),
            TarotCard("The Hanged Man", "Surrender, new perspective, enlightenment"),
            TarotCard("Death", "The end of something, change, the impermeability of all things"),
            TarotCard("Temperance", "Balance, moderation, being sensible"),
            TarotCard("The Devil", "Destructive patterns, addiction, giving away your power"),
            TarotCard("The Tower", "Collapse of stable structures, release, sudden insight"),
            TarotCard("The Star", "Hope, calm, a good omen!"),
            TarotCard("The Moon", "Mystery, the subconscious, dreams"),
            TarotCard("The Sun", "Success, happiness, all will be well"),
            TarotCard("Judgement", "Rebirth, a new phase, inner calling"),
            TarotCard("The World", "Completion, wholeness, attainment, celebration of life"),
            # Minor Arcana cards can be added similarly...
        ]

    def shuffle(self):
        random.shuffle(self.cards)

    def draw(self, number_of_cards):
        return [self.cards.pop() for _ in range(number_of_cards)]

class TarotReading:
    def __init__(self, deck):
        self.deck = deck

    def perform_reading(self, number_of_cards):
        self.deck.shuffle()
        drawn_cards = self.deck.draw(number_of_cards)
        print("Your Tarot Reading:")
        for card in drawn_cards:
            print(card)

if __name__ == "__main__":
    deck = TarotDeck()
    reading = TarotReading(deck)

    number_of_cards = int(input("How many cards would you like to draw? "))
    reading.perform_reading(number_of_cards)
popo
