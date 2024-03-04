# Cryptography Category:

### > Teyvat Tales challenge :

# > Description :

> All tavern owners in Mondstadt are really worried because of the frequent thefts in the Dawn Winery cellars. The Adventurers’ Guild has decided to secure the cellar door passwords using a special cipher device. But the cipher device itself requires various specifications….which the guild decided to find out by touring the entire Teyvat.

> PS: The Guild started from the sands of Deshret then travelled through the forests of Sumeru and finally to the cherry blossoms of Inazuma

In this challenge, we encounter a website with four inputs.

![](https://media.discordapp.net/attachments/1192496321337237504/1214286122444918814/Screen_Shot_2024-03-04_at_7.50.14_PM.png?ex=65f88f13&is=65e61a13&hm=125a23f2ecbb77bab329c34542f8940b314abb071714a8deb04ce081176ce348&=&format=webp&quality=lossless&width=2314&height=1448)

Upon inspecting the source code, we find a JavaScript file containing the correct inputs.

```js
const submitBtn1 = document.getElementById("submit-btn-1");
const firstFour = document.querySelector(".first-four");

const submitBtn2 = document.getElementById("submit-btn-2");
const secFour = document.querySelector(".sec-four");

const submitBtn3 = document.getElementById("submit-btn-3");
const thirdFour = document.querySelector(".third-four");

const submitBtn4 = document.getElementById("submit-btn-4");
const fourthFour = document.querySelector(".fourth-four");


submitBtn1.addEventListener("click", ()=> {
    const inputText1 = document.getElementById("input1").value.trim();

    if (inputText1.toLowerCase() === "enigma m3") {
        firstFour.classList.remove("centered-align");
        firstFour.classList.add("hidden");
    }
    else{
        alert("Incorrect deciphering! Try again!")
    }
});

submitBtn2.addEventListener("click", ()=> {
    const inputText2 = document.getElementById("input2").value.trim();

    if (inputText2.toLowerCase() === "ukw c") {
        secFour.classList.remove("centered-align");
        secFour.classList.add("hidden");
    }
    else{
        alert("Incorrect deciphering! Try again!")
    }
});

submitBtn3.addEventListener("click", ()=> {
    const inputText3 = document.getElementById("input3").value.trim();

    if (inputText3.toLowerCase() === "rotor1 i p m rotor2 iv a o rotor3 vi i n") {
        thirdFour.classList.remove("centered-align");
        thirdFour.classList.add("hidden");
    }
    else{
        alert("Incorrect deciphering! Try again!")
    }
});

submitBtn4.addEventListener("click", ()=> {
    const inputText4 = document.getElementById("input4").value.trim();

    if (inputText4.toLowerCase() === "vi sh wa ct fx") {
        fourthFour.classList.remove("centered-align");
        fourthFour.classList.add("hidden");        
    }
    else{
        alert("Incorrect deciphering! Try again!")
    }
});
```

After submitting them, we receive a picture of encrypted text. 

![](https://media.discordapp.net/attachments/1192496321337237504/1214286121786286210/Screen_Shot_2024-03-04_at_7.40.24_PM.png?ex=65f88f13&is=65e61a13&hm=01c9f1c6d1289b717c36243a96086818ea4a2dcbc6a0fe8592cb18e8900f93d2&=&format=webp&quality=lossless&width=2314&height=1448)

To decrypt it, we employ the Enigma machine, with the correct submissions serving as the settings to decrypt the flag.

![](https://media.discordapp.net/attachments/1192496321337237504/1214286123023728702/Screen_Shot_2024-03-04_at_7.54.20_PM.png?ex=65f88f14&is=65e61a14&hm=0193483510115ab7765c4214f1faac366c4d20a47d947608309ceb35dc88dff4&=&format=webp&quality=lossless&width=2588&height=1292)

FLAG : 
> VishwaCTF{beware_of_tone-deaf_bard}
