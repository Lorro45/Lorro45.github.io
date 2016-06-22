---
title: Game creating
layout: post
author: lawrence.parmenter
permalink: /game-creating/
source-id: 1VnH9gYVM9STB6HbiEdKo-h7Ysnp0ZTIVsuxOupXKe1g
published: true
---
I'm creating a game on micro bit, hier is my brief and some of the script please post ideas if you have any:

Light fowler!

In this game there are multiple levels which the player must pass by collecting all the lights. The player is a small flashing dot on the screen that can move left (press A), right (press B) and down (press AB). They must collect the lights to gain points and pass the level. They can not touch darkness or will lose a life and go back to start ( they can go over space where light was they just can't see the path!). They start with 5 lives. If all rounds are completed there will be a bonus round and then there lives will be added to the score and the score will be displayed.

## Here is some of the script for the first level and whole game: 

// When the BBC micro:bit runs.function onStart(  ) {

function onStart(  ) {

	globals.game = true;

	globals.lives = 5;

	globals.level = 1;

	globals.score = 0;

	while (globals.game == true) {

		

		if (globals.lives == 0) {

			

			globals.game = false;

			microbit.draw(Pattern("01010.01010.00000.01110.10001"));

			

		}

		

		microbit.on(globals.player_X, globals.Player_Y);

		wait(50);

		microbit.off(globals.player_X, globals.Player_Y);

		if (microbit.buttonAPressed) {

			

			wait(50);

			globals.player_X = globals.player_X - 1;

			

		}

		

		else if (microbit.buttonBPressed) {

			

			wait(50);

			globals.player_X = globals.player_X + 1;

			

		}

		

		if (globals.level == 1) {

			

			globals.player_X = 0;

			globals.Player_Y = 2;

			microbit.draw(Pattern("00000.00000.01111.00000.00000"));

			if (( globals.player_X == 4 ) && ( globals.Player_Y == 2 )) {

				

				globals.level = globals.level + 1;

				globals.score = globals.score + 1;

				

			}

			

			else if (globals.Player_Y == 4) {

				

				globals.lives = globals.lives - 1;

				globals.player_X = 0;

				globals.Player_Y = 2;

				

			}

			

			else if (globals.Player_Y == 3) {

				

				globals.lives = globals.lives - 1;

				globals.player_X = 0;

				globals.Player_Y = 2;

				

			}

			

			else if (( globals.player_X == 3 ) && ( globals.Player_Y == 2 )) {

				

				globals.score = globals.score + 1;

				

			}

			

			else if (( globals.player_X == 2 ) && ( globals.Player_Y == 2 )) {

				

				globals.score = globals.score + 1;

				

			}

			

			else if (( globals.player_X == 1 ) && ( globals.Player_Y == 2 )) {

				

				globals.score = globals.score + 1;

				

			}

			

			

		}

		

		else if (microbit.buttonAandBPressed) {

			

			wait(50);

			globals.Player_Y = globals.Player_Y + 1;

			

		}

		

		else if (globals.level == 2) {

			

			microbit.draw(Pattern("10000.11100.00100.00111.00001"));

			globals.player_X = 0;

			globals.Player_Y = 0;

			if (( globals.player_X == 4 ) && ( globals.Player_Y == 0 )) {

				

				globals.score = globals.score - 1;

				globals.player_X = 0;

				globals.Player_Y = 0;

				

			}

			

			else if (( globals.player_X == 1 ) && ( globals.Player_Y == 0 )) {

				

				globals.lives = globals.lives - 1;

				globals.player_X = 0;

				globals.Player_Y = 0;

				

			}

			

			else if (( globals.player_X == 2 ) && ( globals.Player_Y == 0 )) {

				

				globals.lives = globals.lives - 1;

				globals.player_X = 0;

				globals.Player_Y = 0;

				

			}

			

			else if (( globals.player_X == 3 ) && ( globals.Player_Y == 0 )) {

				

				globals.score = globals.score - 1;

				globals.player_X = 0;

				globals.Player_Y = 0;

				

			}

			

			else if (( globals.player_X == 4 ) && ( globals.Player_Y == 4 )) {

				

				globals.level = globals.level + 1;

				globals.score = globals.score + 1;

				

			}

			

			else if (( globals.player_X == 4 ) && ( globals.Player_Y == 1 )) {

				

				globals.lives = globals.lives - 1;

				globals.player_X = 0;

				globals.Player_Y = 0;

				

			}

			

			else if (( globals.player_X == 3 ) && ( globals.Player_Y == 1 )) {

				

				globals.lives = globals.lives - 1;

				globals.player_X = 0;

				globals.Player_Y = 0;

				

			}

			

			else if (( globals.player_X == 2 ) && ( globals.Player_Y == 1 )) {

				

				globals.lives = globals.lives - 1;

				globals.player_X = 0;

				globals.Player_Y = 0;

				

			}

			

			

		}

		

		

	}

	

	

}

