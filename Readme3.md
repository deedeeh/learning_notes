#### Continue Learning Notes - 3

###### Friday 1st June
+ Today I am working on *Methods* in Ruby and I am learning about TDD and Rspec and how testing makes your code flexible and helps to write code that is robust.

Here are few lines of the codes for Rspec:
```Ruby
require_relative '../current_age_for_birth_year.rb'

describe "current_age_for_birth_year method" do
it "returns the age of a person based on the year of birth" do
    age_of_person = current_age_for_birth_year(1984)

    expect(age_of_person).to eq(19)
  end
end
```
And here is to pass the tests:

```Ruby
def
  current_age_for_birth_year(birth_year);
  2003 - birth_year
end
```
