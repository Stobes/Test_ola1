1. Reflections

1.1 Shooting
    Missed shot
    Non-fatal hit
    Bulletproof clothes/accessories
    Non-lethal bullet
    No bullet (?)
    The man knew firstaid

1.2 Alien
    Pick up toothbrush with the dominant hand.
    
    Hold it in the opposite end of the bristle.

    With the non-dominant hand, open the toothpaste tupe by screwing the cap by turning it clockwise until it comes off.

    Pick up the tube, and queeze a small amount (just so it covers the bristle) of the toohtpaste onto the bristles of the toothbrush.

    Wet the boothbrush under some cold water to mositen the bristles.

    Lift the boothbrush to your mouth.

    Position the toothbrush with a slight angle to your teeth/gums
    Start with the bottom teeth.

    Start with brushing the outside of the theeth by moving the brush in gentle motions on the teeths' surface.

    Then continue with the same motion, just at the inner surface now.
    Lastly brush the chewing surfaces of the upperteeth with the same motion
    
    Reapeat the same process, for your lower teeth.

    Don't forget to also brush the tongue to remove bacteria/smell.

    After brushing your teeth for about 2 minutes, spit out the excess toothpaste in the sink.

    Now gently "whip" the toothbrush so any excess water also gets knocked off, so the bristle is as dry as possible.

    Rinse your mouth to remove any remaning toothpaste.

    Rinse your toothbrush under running water to was any leftover toothpaste.

    Place the cap back on the toothpaste tube and screw it on counterclockwise until its sealed.

    Store the toothbrush and the toothpaste in a clean dry place.

    Do it regularly.

2. Two katas
2.1.
    Fahrenheit to celcius converter
    ```
    import unittest

    # Step 2 - green, method implementation
    def fahrenheit_to_celsius(fahrenheit):
        celsius = (fahrenheit - 32) * 5.0/9.0
        return round(celsius, 2)

    # Step 1 - red, will fail initially
    class TestTemperatureConversion(unittest.TestCase):
        def test_fahrenheit_to_celsius_positive(self):
            self.assertEqual(fahrenheit_to_celsius(32), 0)

        def test_fahrenheit_to_celsius_negative(self):
            self.assertEqual(fahrenheit_to_celsius(-40), -40)

    if __name__ == '__main__':
        unittest.main()
    ```
    Celcius to fahrenheit converter
    ```
    import unittest

    # Step 2 - green, method implementation
    def celsius_to_fahrenheit(celsius):
        fahrenheit = (celsius * 9.0/5.0) + 32
        return round(fahrenheit, 2)

    class TestTemperatureConversion(unittest.TestCase):

    # Step 1 - red, will fail initially
        def test_celsius_to_fahrenheit_positive(self):
            self.assertEqual(celsius_to_fahrenheit(0), 32)

        def test_celsius_to_fahrenheit_negative(self):
            self.assertEqual(celsius_to_fahrenheit(-40), -40)
            
    if __name__ == '__main__':
        unittest.main()
    ```
    Roman numeral
    ```
    import unittest
    import random

    # green, method implementation
    def convert_to_roman(arabic):
        roman_numerals = {
            1: 'I',
            4: 'IV',
            5: 'V',
            9: 'IX',
            10: 'X',
            40: 'XL',
            50: 'L',
            90: 'XC',
            100: 'C',
            400: 'CD',
            500: 'D',
            900: 'CM',
            1000: 'M'
        }

        if arabic <= 0 or arabic > 3999:
            raise ValueError("Input out of range (1-3999): {}".format(arabic))

        result = ""
        for x in sorted(roman_numerals.keys(), reverse=True):
            while arabic >= x:
                result += roman_numerals[x]
                arabic -= x

        return result

    # red, will fail initially
    class TestRomanNumeralConversion(unittest.TestCase):
        def test_convert_to_roman(self):
            arabic = random.randint(1, 3999)
            roman = convert_to_roman(arabic)
            self.assertEqual(convert_to_roman(arabic), roman)

    if __name__ == '__main__':
        unittest.main()
    ```
 
3. 3 GIVE YOUR THOUGHTS ON TDD 

    What was positive and good about using TDD?
        The positive was that the code design was more robust (and actually worked as intented). It's very nice that tests actually gives information wether the code works or doesn't work. In the code we made, we thought it was nice that when the test failed, it said what the actual value was and what the expected value was.

    What was annoying or difficult?
        The whole red-green-refactor thought-process was a little hard to understand in the beginning. It felt a little weird to make the code fail at first, and then fix it. 
        Also due to our very limited experience with testing, it was quite difficult to get the idea of how the test should be written, and then actually write it.
       
    What surprised you?
        How easy and stong tests actually is to implement once you'd get the hang of it. The idea of testing seems really nice and we've always thought that when you're in the "real" world, tests seems kind of redundant - but we can conclude that it is not the case!

    Did TDD help you write some tests you wouldn’t otherwise have thought of?
        Well kind of, yes. In the Roman Numeral Kata, we did things alot different than in the temperature converter. Intially we just created very static tests, that only tested if 5 == 'V' and so on.
        However, we thought to make it way more dynamic, meaning that we wanted to be able to test *every* number from 1-3999. We're not quite sure if we implemetned it correctly with the red-green-refactor/tdd principles (it's mostly the reactoring part we're unsure about), but we gave it our best shot!
