># MD Shekh Sadi
> ### **Email:** ***sadiewu12345@gmail.com***

# GoogleTest

- Based on xUnit Architecture
- Portable and Reusable, works on Linux, Mac and Windows
- Writing Unit test code in and for C++

## Steps for googletest
1. clone the ***googletest*** for github
    <a href="https://github.com/google/googletest.git" target="_blank">link</a>
2. inside ***googletest*** directory create a directory called ***build***
3. go inside ***build***
4. Run ***cmake***
    > cmake ..  
    > cmake --build .
5. write our main.cpp file  
    ``` cpp  
    #include<iostream>  
    #include<gtest/gtest.h>  

    using namespace std;

    int main(int argc, char **argv){
        testing::InitGoogleTest(&argc, argv);

        return RUN_ALL_TESTS();
    }
    ```
6. Write ***CMakeLists.txt*** file for Vscode
    ``` cmake
    cmake_minimum_required(VERSION 3.12)

    set(This Example)

    project(${This} C CXX)

    set(CMAKE_C_STANDARD 99)
    set(CMAKE_CXX_STANDARD 11)
    set(CMAKE_POSITION_INDEPENDENT_CODE ON)

    enable_testing()

    add_subdirectory(googletest)

    set(
        Sources 
        main.cpp
    )

    add_executable(
        ${This}
        ${Sources}
    )

    target_link_libraries(${This} PUBLIC
        gtest_main
    )

    add_test(
        Name ${This}
        COMMAND ${This}
    )
    ```
7. Build and Run the program

## Add ***Test*** Cases
 
1. It takes two parameters
    - Test Name
    - Sub Test Name
```cpp
TEST(TestName, SubTest_1){
    ASSERT_TRUE(1 == 1);    
}
TEST(TestName, SubTest_2){
    ASSERT_FALSE(1 == 2);   //Fatal Failure
}
TEST(TestName, SubTest_3){
    EXPECT_TRUE(1==3);  //Non Fatal Failure
}
```

# Assertions
1. Success
2. Non_Fatal Failure
3. Fatal Failure

> 1. EXPECT_EQ() or ASSERT_EQ() -> Equal
> 2. EXPECT_NE() or ASSERT_NE() -> Not equal
> 3. EXPECT_LT() or ASSERT_LT() -> LessThan
> 4. EXPECT_LE() or ASSERT_LE() -> LessThanEqual
> 5. EXPECT_GT() or ASSERT_GT() -> GreaterThan
> 6. EXPECT_GE() or ASSERT_GE() ->GreaterThanEqual  
> *EXPECT -> Non-Fatal Failure (The full program will nun)*   
> *ASSERT -> Fatal Failure (Code will stop after failure)*
## For ***String***
> 1. ASSERT_STREQ() or EXPECT_STREQ() -> Equal
> 2. ASSERT_STRNE() or EXPECT_STRNE() -> Not Equal
> 3. ASSERT_STRCASEEQ() or EXPECT_STRCASEEQ() -> Case Equal
> 4. ASSERT_STRCASENE() or EXPECT_STRCASENE() -> Case Not Equal
