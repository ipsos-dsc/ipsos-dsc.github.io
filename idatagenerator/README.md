
# iDataGenerator 

iDataGenerator - an automation tool to help SW to generate staging / testing data




## Features

- MDD Support : Supports MDD input 
- Multiple Devices Emulation : Desktop , Mobile , Tablet
- Screenshot : Screenshot of Every Question
- Multiple Modes :  GUI and Headless
- Respondent Path : Excel with all respondent Path with Question id
- Respondent Path Graphs : Creates Respondent Graphs 



## How to use ?

 * **You can refer the video below :**

https://github.com/AYadav01DSC/assets/assets/154878702/c68fe402-361a-41d8-a5c2-a615b6ddc215.mp4?width=200&height=200


* **Refer this if video is not enough**

    1. Click on the iDataGenerator progam 
    2. Add your survey link
    3. Enter Number of completes i.e. How many completes you need. __It is limited to   5 instances at time__

    4. Select the mdd file which will have __hints__ that will help the program to lead the survey towards completion.
    __Click on the browse mdd button and browse the mdd file and select.__


   * __*To know how to specify hints in mdd file, please refer this section [How to specify hints in mdd](#how_to_specify_hints_in_mdd)*__

   5. The program has Browser Ui config section which user can configure.
It contains two options

    1. GUI : Which means the browser will open in a window, and walk you through out the survey
    2. Headless : Which means the browser will not be shown to you, but the survey will be filled in the background.
        (You will still be able to see what question the program is on currently on the command prompt which will be shown in Ui)




## [How To specify Hints in mdd](how_to_specify_hints_in_mdd)

***welcome to tutorial on how to specify hints in mdd kindly,
 refer the snippets for different questions types***

* __single punch question__
* __[idatagenerator = "[1,4]"]__ **This specifies that {_1} or {_4} should be punched**

``` 
    Q1 where do you live ?
    [
        idatagenerator = "[1,4]"
    ]
    categorical[1..1]
    {
        _1 "India",
        _2 "Pakistan",
        _3 "United States",
        _4 "Bangladesh"
    }
```
__[idatagenerator = "[1,4]"]__ **This specifies that {_1} and {_4} should be punched**

* __Multi select question__

```
   USRACE4 "Select your Race"
        [
           idatagenerator= "[4,1]"
        ]
    categorical [1..]
    {
        _1 "White",
        _2 "Black or African American",
        _3 "Native American or Alaskan Native",
        _4 "Asian",
        _5 "Pacific Islander",
        _6 "Other race",
        _7 "Prefer not to answer" exclusive,
        _98 "Consent not granted"
    };


```

__[idatagenerator =  "{22:[2]}"]__ **This specifies that on {_22} scale {_2} will be punched**

* __Grid Questions__

```
 Q8 "Please indicate your level of experience with each of the following dating sites or apps."
    [
        idatagenerator = "{22:[2]}"
    ]
    loop
    {
        use full_Brand_list_img -
    } ran fields -
    (
        Q8_scale ""
        categorical [1..1]
        {
            _1 "Never heard of it",
            _2 "Heard of it, but never used it",
            _3 "Used it (or are currently using it)"
        };

    ) expand grid;
    
```

__[ idatagenerator = "[1,2,3]"]__ **This specifies that in bubble ranking {1 ,2 3,} will be checked**

* __BubbleRanking__

```
 Q9 "Rank top 3 brand which you use."
    [
        idatagenerator = "[1,2,3]"
    ]
    
    categorical[1..1]
    {
        _1 "H&M"
        _2 "Allen Soly"
        _3 "Crocodile"
        _4 "Raymond"
        _5 "Levis"

    }ran;
    
```


__[ idatagenerator = "[3]"]__ **This specifies that in Volume control to  {_3}**

* __Volume Control__

```
 Q10 "How much do you Agree with this this brand"
    [
        idatagenerator = "[3]"
    ]
    
    categorical[1..1]
    {
        _1 ""
        _2 ""
        _3 ""

    }ran;
    
```


__[ idatagenerator = "["Walter White"]"]__ **This specifies that in TextBox "Walter white" will be punched (if there is multiple values if will check another TextBox to punch the value)**

* __Text Box__

```
 Q11 "What is your Name ?"
    [
        idatagenerator = "["Walter White"]" or  idatagenerator = 
        "['Walter White','John Doe']"  
    ]
    text[1..4000];
    
```


* __Slider Question__

```
 All The Slider Question will automatically scrolled out with random value   
```


__[ idatagenerator = "["Walter White"]"]__ **This specifies that in select "Walter white" from the dropdown**
* __Select Box__
```
 Q11 "Select Your Age."
    [
        idatagenerator = "["Walter White"]" or  idatagenerator = 
        "['Walter White','John Doe']"  
    ]
    
```





## FAQ

#### iDatagenerator is not working out of office why ?
For security reasons,
iDatagenerator will not work outside office, you need to be in office network. if you still want to use it you can connect vpn and use it .

#### I am using it in headless mode but not getting completes ? 

you have to run it once in gui mode, to ensure it is working fine if you are not getting completes.





### Authors & feedback

* [Ajit Yadav](https://github.com/mr-internetix)
* [Piyush patre](https://github.com/piyushpatro)

  
_for any queries and feedback : ajit.yadav2@ipsos.com , piyush.patre@ipsos.com_