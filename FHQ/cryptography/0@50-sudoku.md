# Sudoku #11
**Description:**

***ENG***
> We managed to intercept the [corporate conversation]((http://webcrypt.org/#SFpa2C8DvxyYFeLI01aSpw.rOPLYDVzdfc.ofkKNSGCqJVsm5Hiwz1PwhZ8R02gFyWvUw). Help us to decrypt it!

---

***RU***
> Нам удалось перехватить [корпоративную переписку](http://webcrypt.org/#SFpa2C8DvxyYFeLI01aSpw.rOPLYDVzdfc.ofkKNSGCqJVsm5Hiwz1PwhZ8R02gFyWvUw). Помогите нам расшифровать её! 

![sudoku](/FHQ/files/cryptography/sudoku.jpeg)

## Writeup

We see that we need to solve this sudoku puzzle to get 11 numbers in order that is shown as indices in every red square. I found this very useful online [sudoku solver](https://www.sudoku-solutions.com) and I got this answer.

![sudoku-solved](/FHQ/images/cryptography/sudoku-solved.png)

The numbers in marked cells in the right order are `37818456633`. I suppose, that this is acrually a passwort to that enciphered corporated conversation. After we fill the password field with those numbers we get `you_can_go_home:)`. Voila.

Flag: `you_can_go_home:)`

### Link

https://freehackquest.com/?quest=11
