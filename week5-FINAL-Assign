//Week 5 Coding Assignment - Menu App

/*The code below creates a menu app for smoothies.
This code contains three classes: 1- for a list of ingredients, 2- for smoothie name, and 
3- the actual menu. Several methods were added to some of the classes for proper functionality
of the app.*/

//SECTION - Class for list of smoothie ingredients:
class Ingredient {
  constructor(proteinPowder, fruits, greens, liquid, other) {
    this.proteinPowder = proteinPowder;
    this.fruits = fruits;
    this.greens = greens;
    this.liquid = liquid;
    this.other = other;
  }
} //NOTE - end of code for Class Ingredient.

//SECTION - Class for smoothie name:
class Smoothie {
  constructor(name) {
    this.name = name;
    this.ingredients = []; //an array that holds the ingredients
  } 

  //ANCHOR -A method to add an ingredient:
  addIngredient(ingredient) {
    if (ingredient instanceof Ingredient) { 
      this.ingredients.push(ingredient); //the ingredient gets pushed into the array
    } else {
      throw new Error(
        `This is not an ingredient; please correct. ${ingredient}`
      );
    }
  }
} //NOTE - end of code for Class Smoothie.

//SECTION -Class for the menu and sub-menu:
class Menu {
  constructor() {
    this.smoothies = []; //initializing the smoothies
    this.selectedSmoothie = null; //create a variable for whatever smoothie is selected.
  }

  //ANCHOR - A method to start the app with a switch statement for user options:
  start() {
    let selection = this.MainMenuOptions();

    while (selection != 0) {
      switch (selection) {
        case "1":
          this.createSmoothie();
          break;
        case "2":
          this.viewSmoothie();
          break;
        case "3":
          this.deleteSmoothie();
          break;
        case "4":
          this.displaySmoothies();
          break;
        default:
          selection = 0;
      }
      selection = this.MainMenuOptions();
    }
    alert("The End!"); //if user selects '0' this alert will pop up because the loop did not run.
  }   
  
//ANCHOR - A method to show menu options for the prompts:
  MainMenuOptions() {
    //'return' - returning the input that comes back from what the user enters when prompted.
    return prompt(`  
         0) exit
         1) enter a smoothie name
         2) view a smoothie
         3) delete a smoothie
         4) list all smoothies
    `);
  }

  //ANCHOR - A method for the sub-menu when user selects 'view a smoothie':
  SmoothieMenuOptions(smoothieInfo) {
    return prompt(`
     0) go back
     1) add an ingredients list
     2) delete an ingredients list
    ---------------------
     ${smoothieInfo}
     `);
  }

  //ANCHOR - A method to list all of the smoothies:
  displaySmoothies() {
    let smoothieString = ""; //building a string that contains all the data for the smoothies
      for (let i = 0; i < this.smoothies.length; i++) {
        smoothieString += i + ") " + this.smoothies[i].name + "\n"; //array of smoothie names 
    }
    console.log(smoothieString);
    alert(smoothieString);   
  }

  //ANCHOR - A method to create a smoothie:
  createSmoothie() {
    let name = prompt("Enter a smoothie name");
    this.smoothies.push(new Smoothie(name)); //adding a new smoothie to the array
  }

  //ANCHOR - A method to view a smoothie and associated data that the user entered:
  viewSmoothie() {
    let index = prompt(
      "to view a smoothie and list of ingredients, enter index number:"
    );
    if (index > -1 && index < this.smoothies.length) { //validating user input
      this.selectedSmoothie = this.smoothies[index];
      let description = "Smoothie Name: " + this.selectedSmoothie.name + "\n"; 
        for (let i = 0; i < this.selectedSmoothie.ingredients.length; i++) {
        //for loop: need to iterate through the array of the list of ingredients
        description += i + ") " +
          this.selectedSmoothie.ingredients[i].proteinPowder + ', '
           +
          this.selectedSmoothie.ingredients[i].fruits + ', '
           +
          this.selectedSmoothie.ingredients[i].greens + ', '
           +
          this.selectedSmoothie.ingredients[i].liquid + ', '
           +
          this.selectedSmoothie.ingredients[i].other;
      }
      console.log(description);
      alert(description);
    
  //ANCHOR - A switch statement for user to add or delete a list of ingredients:      
      let selection = this.SmoothieMenuOptions(description); 
      switch (selection ) {
        case "1":
          this.createIngredient();
          break;
        case "2":
          this.deleteIngredient();
      }
    }
  }

  //ANCHOR - A method to delete a smoothie from the menu:
  deleteSmoothie() {
    let index = prompt("To delete a smoothie, please enter the index number:");
    if (index > -1 && index < this.smoothies.length) {
      this.smoothies.splice(index, 1);
    }
  }

  //ANCHOR - A method for creating a list of ingredients:
  createIngredient() {
    let proteinPowder = prompt("Enter protein powder:");
    let fruits = prompt("Enter fruits:");
    let greens = prompt("Enter greens:");
    let liquid = prompt("Enter liquid base:");
    let other = prompt("Enter other ingredients");
    this.selectedSmoothie.ingredients.push(
      new Ingredient(proteinPowder, fruits, greens, liquid, other) 
    );
  }

  //ANCHOR - A method for deleting a list of ingredients:
  deleteIngredient() {
    let index = prompt(
      "Enter index number to delete an ingredients list:"
    );
    if (index > -1 && index < this.selectedSmoothie.ingredients.length) {
      this.selectedSmoothie.ingredients.splice(index, 1); 
  }
} 
} //NOTE - End of Class Menu

//SECTION - A method to create an instance of the menu app and mplementation of the app:
let menu = new Menu(); 
menu.start(); 