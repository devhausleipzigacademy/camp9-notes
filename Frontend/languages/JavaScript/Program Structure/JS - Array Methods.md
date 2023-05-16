## Push

The **`push()`** method adds one or more elements to the end of an array and returns the new length of the array.



```javascript

const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

pokemon.push("ditto");

console.log(pokemon) // ["pikachu", "bulbasaur", "charmander", "squirtle", "diito"]

console.log(pokemon.push("ratata")) //6

  

const newPokemon = ["raichu", "charizard", "venusaur", "blastoise"]

pokemon.push(newPokemon)

console.log(pokemon) //["pikachu", "bulbasaur", "charmander", "squirtle", "diito" , "ratata", ["raichu", "charizard", "venusaur", "blastoise"] ]

//HOW WOULD YOU SOLVE THIS PROBLEM?
//so that the return output is:

// ["pikachu", "bulbasaur", "charmander", "squirtle", "diito" , "ratata", "raichu", "charizard", "venusaur", "blastoise"]


```

## Pop

The **`pop()`** method removes the **last** element from an array and returns that element. This method changes the length of the array.


```Javascript
const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

pokemon.pop()

console.log(pokemon) // ["pikachu", "bulbasaur", "charmander"]

console.log(pokemon.pop()) // charmander

```

## Unshift

The **`unshift()`** method adds one or more elements to the beginning of an array and returns the new length of the array.


```js
const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];
pokemon.unshift("ditto");

console.log(pokemon) // ["ditto","pikachu", "bulbasaur", "charmander", "squirtle"]

console.log(pokemon.unshift("charizard")) // 6

console.log(pokemon) // ["charizard", "ditto","pikachu", "bulbasaur", "charmander", "squirtle"]

```

## Shift

The **`shift()`** method removes the **first** element from an array and returns that removed element. This method changes the length of the array.

```js
const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

const firstPokemon = pokemon.shift();

console.log(pokemon) // ["bulbasaur", "charmander", "squirtle"]

console.log(firstPokemon) // pikachu

console.log(pokemon.shift()) // bulbasaur
```

## Splice

The **`splice()`** method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.

Splice(start, deleteCount?, item?)


```js
// many use cases
// 1.

const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon); //["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.splice(1)) // ["bulbasaur", "charmander", "squirtle"];

console.log(pokemon) // ["pikachu"];

// it removed everything from the index position 1

// 2.

const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon); //["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.splice(3)) // ["squirtle"]

console.log(pokemon) // ["pikachu", "bulbasaur", "charmander"]

//3

const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon); //["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.splice(1, 2)) // ["bulbasaur", "charmander"]

console.log(pokemon) // ["pikachu", "squirtle"]

//4

const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon); //["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.splice(1, 0, "ditto")) // []

console.log(pokemon) // ["pikachu", "ditto", "bulbasaur", "charmander", "squirtle"]


//5

const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon); //["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.splice(1, 1, "ditto")) // ["bulbasaur"]

console.log(pokemon) // ["pikachu", "ditto", "charmander", "squirtle"]


```


## Slice

The **`slice()`** method returns a [shallow copy](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy) of a portion of an array into a new array object selected from `start` to `end` (`end` not included) where `start` and `end` represent the index of items in that array. The original array will not be modified.

```js
const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

const whatPokemonIsThis = pokemon.slice(2) 

console.log(whatPokemonIsThis) // ["charmander", "squirtle"]

console.log(pokemon) // ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.slice(1,3)) // ["bulbasaur", "charmander"]

console.log(pokemon.slice(1,2)) // ["bulbasaur"]

console.log(pokemon.slice(-1)) // ["squirtle"]

```

## Concat

The **`concat()`** method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

```js
const ash = ["pikachu", "bulbasaur", "charmander"]
const brock = ["geodude", "onyx"]
const teamAsh = ash.concat(brock)

console.log(teamAsh) //["pikachu", "bulbasaur", "charmander", "geodude", "onyx"]

```

## IndexOf

The **`indexOf()`** method returns the first index at which a given element can be found in the array, or -1 if it is not present.

```js
const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.indexOf("bulbasaur"))  //1

pokemon.push("bulbasaur")

console.log(pokemon) //["pikachu", "bulbasaur", "charmander", "squirtle", "bulbasaur"]

console.log(pokemon.indexOf("bulbasaur", 1)) // 4

console.log(pokemon.indexOf("raichu")) // what should be the expected result?

```

## find

The **`find()`** method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) is returned.

```js
const pokemonLevel = [5 , 7, 12, 35, 38, 11]

const firstPokemonMoreThanLevelTen = pokemonLevel.find(el => el > 10)
console.log(firstPokemonMoreThanLevelTen) //12

const firstPokemonMoreThanLevelHunderd = pokemonLevel.find(el => el > 100)
console.log(firstPokemonMoreThanLevelHundred) // undefined


const pokemon = [
	{ name: "pikachu", level: 45},
	{ name: "bulbasaur", level: 30},
	{ name: "charmandar", level: 47},
	{ name: "squirtle", level: 23}
]

function isPikachu(poke) {
 return poke.name === "pikachu"
}

console.log(pokemon.find(isPikachu)) // { name: "pikachu", level: 45}


```

## includes

The **`includes()`** method determines whether an array includes a certain value among its entries, returning `true` or `false` as appropriate.

```js
const pokemon = ["pikachu", "bulbasaur", "charmander", "squirtle"];

console.log(pokemon.includes("pikachu")) //true
console.log(pokemon.includes("franz")) //false

```

## for Each

The **`forEach()`** method executes a provided function once for each array element.

```js
const pokemonLevel = [5 , 7, 12, 35, 38, 11]
const newPokemonLevel = []

pokemonLevel.forEach((level) => {newPokemonLevel.push(level + 1)})

console.log(newPokemonLevel) //[6 , 8, 13, 36, 39, 12]
```


## filter

The **`filter()`** method creates a [shallow copy](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy) of a portion of a given array, filtered down to just the elements from the given array that pass the test implemented by the provided function.

```js
const pokemonLevel = [5 , 7, 12, 35, 38, 11]

const biggerThanLevelTen = pokemonLevel.filter(level => level > 10);
console.log(pokemonLevel) // [12, 35, 38, 11]

```
