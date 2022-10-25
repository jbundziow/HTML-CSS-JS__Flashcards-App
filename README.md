# HTML/CSS/JS \_\_ Flashcards app

## Description

Flashcards app is an easy way to learn English vocabulary. Insert data what you neeed to the database, print the table and learn your new vocabulary. Finally, exercise it by using flashcards.

//@TODO: GIF HERE

> Description of the photo

## How to use?

On the start screen select the user (database), category (table) and mode. Then press "Start" button.

//@TODO: mainpage screen

> Description of the photo

App can be used in two different modes:

### Learn mode

Learn mode allows user to look inside created table in database. User can learn vocabulary by the classic method - reading words in polish language and their translation in english. Table can be easy converted into .pdf file or printed by clicking button below the table.

//@TODO: learnmode screen

> Description of the photo

### Flashcards mode

Flashcards mode is the main feature of this app. On the purple card is displayed a random word in polish language. User has to translate it and result is presented by the red card (wrong answer) or the green card (correct answer). After giving an incorrect answer user has to try again until the correct answer is given.

//@TODO: purple card

> Description of the photo
> //@TODO: green card
> Description of the photo
> //@TODO: red card
> Description of the photo

App also collects the data about efficiency and learning time in current session and shows everything in real time below the card section.

## Editing database files

It's not possible to make changes in the database using Javascript, so the database files can be edited by a free tool "DB Browser for SQLite" (https://sqlitebrowser.org). Inside the file can be created multpile tables. It's recommended to sort vocabulary by category.

//@TODO: db1 photo

> Description of the photo

Inside each table should be six columns with names "eng1, eng2, eng3, pol1, pol2, pol3". There are 3 possible meanings of the same word in both languages. An example is shown in the photo below.

//@TODO: db2 photo

> Description of the photo

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
link here
```

## How to run?

#### Option 1

- Just open the link above, in section "Live preview".

#### Option 2

- Download all files
- Open index.html using a web server
