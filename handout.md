# Tic Tac Toe with React

## Components

### `Square` Component
```javascript
function Square({ value, onSquareClick }) {
  return (
    <button className="square" onClick={onSquareClick}>
      {value}
    </button>
  );
}
```
- Represents a square in the Tic Tac Toe board.

### `Board` Component
```javascript
function Board({ squares, onPlay, xIsNext }) {
  function handleClick(i) {
    const nextSquares = [...squares];
    nextSquares[i] = xIsNext ? 'X' : 'O';
    onPlay(nextSquares);
  }
  const winner = calculateWinner(squares);
  let status = winner ? 'Winner: ' + winner : 'Next player: ' + (xIsNext ? 'X' : 'O');
  return (
    <>
      <div className="status">{status}</div>
    </>
  );
}
```
- Renders the Tic Tac Toe board and handles game logic.

### `Game` Component
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
- Manages the overall game state.

## Helper Function

### `calculateWinner`
```javascript
function calculateWinner(squares) {
  const lines = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8],
    [0, 3, 6], [1, 4, 7], [2, 5, 8],
    [0, 4, 8], [2, 4, 6]
  ];
  for (let i = 0; i < lines.length; i++) {
    const [a, b, c] = lines[i];
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
      return squares[a];
    }
  }
  return null;
}
```
- Determines the winner of the game.
