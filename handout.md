# React Tic-Tac-Toe Code Explanation

This code implements a simple Tic-Tac-Toe game using React. Let's break down the different components and their functionality:

## Square Component
The `Square` component represents a single square on the Tic-Tac-Toe board. It receives two props:
- `value`: the value of the square (either 'X', 'O', or `null`)
- `onSquareClick`: a function that is called when the square is clicked

```javascript
function Square({ value, onSquareClick }) {
  return (
    <button className="square" onClick={onSquareClick}>
      {value}
    </button>
  );
}
```

## Board Component
The `Board` component is responsible for rendering the entire Tic-Tac-Toe board. It receives three props:
- `squares`: an array of 9 elements representing the current state of the board
- `onPlay`: a function that is called when a square is clicked
- `xIsNext`: a boolean indicating whether it's X's or O's turn

```javascript
function Board({ squares, onPlay, xIsNext }) {
  function handleClick(i) {
    // ... (code omitted for brevity)
  }

  const winner = calculateWinner(squares);
  let status;
  if (winner) {
    status = 'Winner: ' + winner;
  } else {
    status = 'Next player: ' + (xIsNext ? 'X' : 'O');
  }

  return (
    // ... (JSX elements omitted for brevity)
  );
}
```

## Game Component
The `Game` component is the top-level component that manages the overall game state. It uses the `useState` hook to maintain the following state:
- `squares`: an array of 9 elements representing the current state of the board
- `xIsNext`: a boolean indicating whether it's X's or O's turn

```javascript
export default function Game() {
  const [squares, setSquares] = useState(Array(9).fill(null));
  const [xIsNext, setXIsNext] = useState(true);

  function handlePlay(nextSquares) {
    setSquares(nextSquares);
    setXIsNext(!xIsNext);
  }

  return (
    <div className="game">
      <div className="game-board">
        <Board squares={squares} onPlay={handlePlay} xIsNext={xIsNext} />
      </div>
    </div>
  );
}
```
