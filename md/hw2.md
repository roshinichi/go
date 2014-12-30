#POKEDEX->Arceus
***
###_This program displays a Pokemon's data according to its best stats_


```go
package main

import (
	"encoding/json" //includes json package better formatting
	"fmt"
)

type Pokemon struct {
	Name  string
	HP    int
	Atk   int
	Def   int
	SAtk  int
	SDef  int
	IV    int
	Moves []Move //array
}

type Move struct {
	Name     string
	Type     string
	Category string
	Power    int

	Accuracy float64
}

func main() {
	var intro string
	intro = "This program displays the info of a pokemon\n"

	fmt.Println(intro)
	pm1 := Pokemon{
		Name: "Arceus",
		/* following lines define variables of this pokemon */
		HP:   444,
		Atk:  372,
		Def:  372,
		SAtk: 372,
		SDef: 372,
		IV:   186,
	}

	move1 := Move{
		Name:     "Earth Power",
		Type:     "Ground",
		Category: "Special",
		Power:    80,

		Accuracy: 100,
	}
	move2 := Move{
		Name:     "Judgement",
		Type:     "Normal",
		Category: "Special",
		Power:    100,

		Accuracy: 100,
	}
	move3 := Move{
		Name:     "Earthquake",
		Type:     "Ground",
		Category: "Physical",
		Power:    100,

		Accuracy: 100,
	}
	move4 := Move{
		Name:     "Extreme Speed",
		Type:     "Normal",
		Category: "Physical",
		Power:    80,

		Accuracy: 100,
	}
	pm1.Moves = append(pm1.Moves, move1) //append:push to Move array
	pm1.Moves = append(pm1.Moves, move2)
	pm1.Moves = append(pm1.Moves, move3)
	pm1.Moves = append(pm1.Moves, move4)
	/*
		@Marshal function
		@returns the JSON encoding
	*/
	j, _ := json.MarshalIndent(pm1, "|", "   ")
	fmt.Println(string(j))
	fmt.Println("End of Arceus")
}
```
