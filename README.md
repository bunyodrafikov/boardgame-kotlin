### Board

Your task is to implement interfaces SquareBoard and GameBoard.

#### SquareBoard

SquareBoard stores the information about the square board and all the cells on it. It allows to get a cell by its indexes, get parts of columns and rows on a board, or get a specified neighbour of a cell.

Note that the numbering of cells starts with 1, not with 0. A board of a width 2 consists of the following cells:

(1, 1) (1, 2)

(2, 1) (2, 2)

For the following examples, we'll use this board of a width 2: `val board = createSquareBoard(2)`

If you call `board.getCellOrNull(3, 3)` for such board, you'll get null as the result, because the board doesn't have a cell with such coordinates. The function `Board.getCell` should throw `IllegalArgumentException` for incorrect values of i and j.

You can write `board.getRow(1, 1..2)` or `board.getRow(1, 2 downTo 1)`, and you'll get the lists of cells [(1, 1), (1, 2)] and [(1, 2), (1, 1)] accordingly. Note how using the range 2 downTo 1 returns a row in a reversed order. You can use any range to get a part of a column or a row.

Note that getRow and getColumn should return a list containing only the cells that belong to the board if the range is larger than the board limits and ignore other indexes, thus, `board.getRow(1, 1..10)` should return [(1, 1), (1, 2)].

The neighbours of a cell (1, 1) depending on the direction should be:

- Direction.UP - null     
- Direction.LEFT - null     
- Direction.DOWN - (2, 1) 
- Direction.RIGHT - (1, 2)

Create only width * width cells; all the functions working with cells should return existing cells instead of creating new ones.

#### GameBoard

GameBoard lets to store the values in board cells, update them, and ask the general information about the stored values (like any, all etc.) Note that GameBoard extends SquareBoard.

See TestSquareBoard and TestGameBoard for examples.