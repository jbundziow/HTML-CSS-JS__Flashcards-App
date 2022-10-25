# HTML/CSS/JS \_\_ Flashcards app

## Description

Flashcards app is an easy way to learn English vocabulary. Insert data what you need to the database, print the table and learn your new vocabulary. Finally, exercise it by using flashcards.

![main](https://user-images.githubusercontent.com/102864070/197813013-178170c8-9b2f-4e67-ad44-962412d8f11d.gif)


## How to use?

On the start screen select the user (database), category (table) and mode. Then press "Start" button.

![mainpage](https://user-images.githubusercontent.com/102864070/197813251-cca96833-6cc1-4ea9-8719-10124a41a9ad.png)
> Mainpage.

App can be used in two different modes:

### Learn mode

Learn mode allows user to look inside created table in database. User can learn vocabulary by the classic method - reading words in polish language and their translation in english. Table can be easy converted into .pdf file or printed by clicking button below the table.

![learnpage](https://user-images.githubusercontent.com/102864070/197813447-c434eb47-07c2-43c6-8ca9-5a2a803d5b64.png)
> Learn page.

![print](https://user-images.githubusercontent.com/102864070/197814553-12c3ee50-d419-4e1e-b121-073effc247b7.png)
> Table ready to be printed.

### Flashcards mode

Flashcards mode is the main feature of this app. On the purple card is displayed a random word in polish language. User has to translate it and result is presented by the red card (wrong answer) or the green card (correct answer). After giving an incorrect answer user has to try again until the correct answer is given.

![checkcard](https://user-images.githubusercontent.com/102864070/197813597-fb5a3626-05ad-4e24-9c81-53fb1ddc85d2.png)
> Card to be filled by user.

![greencard](https://user-images.githubusercontent.com/102864070/197813872-265415ed-42ad-4aa3-9532-ef93a60ac890.png)
> Correct-answer card

![redcard](https://user-images.githubusercontent.com/102864070/197813974-21031f83-52fa-46fa-9fa3-124074c0d37d.png)
> Uncorrect-answer card

App also collects the data about efficiency and learning time in current session and shows everything in real time below the card section.

## Editing database files

It's not possible to make changes in the database using Javascript, so the database files can be edited by a free tool "DB Browser for SQLite" (https://sqlitebrowser.org). Inside the file can be created multpile tables. It's recommended to sort vocabulary by category.

![db1](https://user-images.githubusercontent.com/102864070/197814083-69b41608-c616-4744-bd33-84f027d76c8b.png)
> Database look in "DB Browser for SQLite"

Inside each table should be six columns with names "eng1, eng2, eng3, pol1, pol2, pol3". There are 3 possible meanings of the same word in both languages. An example is shown in the photo below.

![db2](https://user-images.githubusercontent.com/102864070/197814346-72b5ad59-1c29-4530-988c-86e7306c0d22.png)
> Database table contents.

Remember also to add your database name to the "user" section in index.html and enter the table name inside script.js file.

#### index.html:

```html
<div class="select1-container">
  <label for="select-database">Select user:</label>
  <select class="select-database">
    <option value="arthur.sqlite">Arthur</option>
    <option value="william.sqlite">William</option>
  </select>
</div>
```

#### script.js:

```javascript
const displayUserTables = (user) => {
  switch (user) {
    case "arthur.sqlite":
      selectTable.innerHTML = `
          <option value="food">food</option>
          <option value="school">school</option>
          <option value="travelling">travelling</option>
          `;
      break;

    case "william.sqlite":
      selectTable.innerHTML = `
            <option value="colors">colors</option>
            <option value="months">months</option>
            `;
      break;

    default:
      console.error(`Problem with displayUserTables().`);
      break;
  }
};
```

## Demo live preview

```sh
https://flashcards-app-public.vercel.app/
```

## How to run?

#### Option 1

- Just open the link above, in section "Live preview".

#### Option 2

- Download all files
- Open index.html using a web server
