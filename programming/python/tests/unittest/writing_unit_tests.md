Unit-Testing ... Test each individual unit of code (typically a METHOD) in isolation
                 See if it responds the expected way !

When dealing with a small unit of an application ... Clear understanding of its responsibilities and the things that can go wrong 

Becomes obvious ... have you broken the code into good-sized units ?
  Do I have to write MANY ... different tests to cover all possibilities that method can go through 
    Then my-method is too LARGE ... should consider refactoring it 

Good rule of thumb ... Ten(10) lines

Test Driven Development (TDD)

Checking Values with the ASSERTEQUALS Method
--------------------------------------------
(x) Have some working code 
(x) Write the test to check it and see if you pass the argument --> get expected result

Standard naming convevtions : <Class-name-under-test>_test.py
calculate_test.py

********************************************************
import unittest

from app.calculate import Calculate

class TestCalculate(unittest.TestCase):
  def setUp(self):
    self.calc = Calculate()

  def test_add_method_returns_correct_result(self):
    self.assertEqual(4, self.calc.add(2,2))

if __name__ == '__main__':
  unittest.main()

********************************************************

The setUp() method ... executed before each test 
  Define my application-instance only once ... use it in many tests

test method naming ... test_<what-it-does>

assertEqual(value1, value2) ... checks if value1 EQ to value2

# ** Checking Exception Handling with ASSERTRAISES **
---------------------------------------------
Definition:
  The <assert>