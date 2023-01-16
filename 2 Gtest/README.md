># MD Shekh Sadi
> ### **Email:** ***sadiewu12345@gmail.com***

## ***It is possible to write more than one assertion statement in a single test case. But it is not recommended.*** 

# Stepts for writing unit test:
Any unit test must have these 3 parts:
1. Arrange
2. Act
3. Assert

```cpp
TEST(TestName, increment_by_5){
    //Arrange
    int value = 100;
    int increment = 5;

    //Act
    value = value + increment;

    //Assert
    ASSERT_EQ(value, 105);
}
```

## Behaviour or unit test
1. Run extreamely fast (within Milisecond)
2. Must be able to run independently
3. Doesn't depend upon any external input
