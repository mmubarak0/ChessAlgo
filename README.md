* [Pawn pesudo code](#pawn-pesudo-code)
* [Bishop pesudo code](#bishop-pesudo-code)
* [Knight pesudo code](#knight-pesudo-code)
* [Rook pesudo code](#rook-pesudo-code)
* [King pesudo code](#king-pesudo-code)
* [Queen pesudo code](#queen-pesudo-code)


> So, my logic will be like this  
<span style="color:#ff0;"> </span>
<span style="color:#0f0;"> </span>

* ## <span style="color:#0f0;"> The Player (*first click*) </span>
    *	The board in the screen player will use the mouse to select a piece  
* ## <span style="color:#ff0;">My work (*on the first click*) </span>
    *	take that selected piece tag >> let’s say it is a **pawn**  
    *	In the Board Manager scripts, it will load the “pawn class script”  
    *	Pawn script check tells you how the pawn will behave and move 
    *	And let you know all the valid moves and invalid moves  
    *	Then the Board manager decides based on this information what to do  

* ##  <span style="color:#0f0;"> The Player (*second click*)  </span>
    *	select another empty or non-empty square let’s say he selects an empty square first  
* ## <span style="color:#ff0;"> My work (*on second click* <span style="color:#990;">(empty square)</span>)  </span>
    *	Check if the selected square is empty or not if ok then continue  
    *	From the loaded piece script is this move legal?
    *	If yes move the previously selected piece to the selected square
    *	else show a message saying illegal move and tell why?
    *	Is there a checkmate already? is this piece pinned and moving it will cause a checkmate? is this an illegal move? **Tricky important**
* ## <span style="color:#ff0;"> My work (*on second click* <span style="color:#990;"> (non-empty square) </span>)  </span>
    *	From the loaded piece script is this move legal?
    *	If yes move the previously selected piece to the selected square
    *	But before moving the piece at this position outside of the board
    *	else show a message saying illegal move and tell why?
    *	Is there a checkmate already? is this piece pinned and moving it will cause a checkmate? is this an illegal move? * Tricky important *  

* ## <span style="color:#0f0;"> Flip the board: `two-player mode`)) adding computer `ai` later </span>

    ```csharp
    PlayerControl.Color = !(PlayerControl.Color)
    ```


<!-- body -->


* ## Pawn pesudo code:

    ```python
    # This will return the block position that has been selected by the mouse
    Current_position = board.Get_mouse_position()
    String [,] Board = new Board [8, 8]
    # The pawn can move up one time at any state except at the initial position for his color
    # The pawn can move up two times only if he is at his initial position for his color
    for i in range (2):
        if ([Current position.x, Current position.y + 1] == empty_square):
            Possible_moves.Append([Current position.x, Current position.y + 1])
        if Current_position.y != 2 # 2 for White or 7 for Black:
            break
        # He can move right or left if there is a piece beside him 
        if Board[Current_position.x+1, Current_position.y] has black_piece and  Board[Current_position.x+1, Current_position.y+1] == empty_square:
            # move up right
            Possible_moves.Append([Current_position.x+1, Current_position.y + 1])

        if Board[Current_position.x-1, Current_position.y] has black_piece and  Board[Current_position.x-1, Current_position.y+1] == empty_square:
            # move left
            Possible_moves.Append([Current_position.x-1, Current_position.y + 1])
    ```

* ## Bishop pesudo code:
* ## Knight pesudo code:
* ## Rook pesudo code:
* ## King pesudo code:
* ## Queen pesudo code:

</br>
</br>
<!-- body -->

 ```

 1	R	N	B	K	Q	B	N	R
 2	P	P	P	P	P	P	P	P
 3 								
 4								
 5								
 6					 			
 7	p	p	p	p	p	p	p	p
 8	r	n	b	q	k	b	n	r
 
         a	b	c	d	e	f	g	h
 ```
