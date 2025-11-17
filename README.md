# Pokemon Draft League Replays

A simple website to host Pokemon Showdown battle replays for a 6-player draft league.

Each week features 3 matchups, with each matchup being a best-of-3 series (2-3 games).

## Structure

```
pokemon-draft-league-replays/
├── index.html          # Main page
├── style.css           # Styling
├── replays/            # Replay files directory
│   ├── week1/
│   │   ├── battle1-game1.html
│   │   ├── battle1-game2.html
│   │   ├── battle1-game3.html
│   │   ├── battle2-game1.html
│   │   ├── battle2-game2.html
│   │   └── ...
│   ├── week2/
│   └── ...
└── README.md
```

## How to Add New Replays

### Step 1: Save Replay Files

1. After each game on Pokemon Showdown, download the replay as an HTML file
2. Create a folder for the week if it doesn't exist: `replays/week#/`
3. Save the replay HTML files in the appropriate week folder
4. Name them descriptively using this pattern:
   - `battle1-game1.html`, `battle1-game2.html`, `battle1-game3.html` (if it goes to 3 games)
   - `battle2-game1.html`, `battle2-game2.html` (if it only goes to 2 games)
   - etc.

### Step 2: Update index.html

Open `index.html` and find the `leagueData` object (around line 23). Add a new week entry:

```javascript
const leagueData = {
    weeks: [
        {
            weekNumber: 1,
            battles: [
                {
                    player1: "Player 1",
                    player2: "Player 2",
                    score: "2-1",  // Format: "player1Score-player2Score"
                    games: [
                        "replays/week1/battle1-game1.html",
                        "replays/week1/battle1-game2.html",
                        "replays/week1/battle1-game3.html"
                    ]
                },
                {
                    player1: "Player 3",
                    player2: "Player 4",
                    score: "2-0",
                    games: [
                        "replays/week1/battle2-game1.html",
                        "replays/week1/battle2-game2.html"
                    ]
                },
                {
                    player1: "Player 5",
                    player2: "Player 6",
                    score: "2-1",
                    games: [
                        "replays/week1/battle3-game1.html",
                        "replays/week1/battle3-game2.html",
                        "replays/week1/battle3-game3.html"
                    ]
                }
            ]
        },
        // Add new weeks here
        {
            weekNumber: 2,
            battles: [
                {
                    player1: "Player 1",
                    player2: "Player 3",
                    score: "2-0",
                    games: [
                        "replays/week2/battle1-game1.html",
                        "replays/week2/battle1-game2.html"
                    ]
                },
                // ... more battles
            ]
        }
    ]
};
```

**Notes:** 
- Each battle can have 2 or 3 games depending on how the best-of-3 series went. Just include the games that were actually played.
- The `score` field shows the final series score in "X-Y" format (player1's wins - player2's wins). For example, "2-1" means player1 won 2 games and player2 won 1 game.

### Step 3: Commit and Push

```bash
git add .
git commit -m "Add week X replays"
git push
```

## Setting Up GitHub Pages

1. Go to your repository settings on GitHub
2. Navigate to "Pages" in the left sidebar
3. Under "Source", select the branch you want to deploy (usually `main` or `master`)
4. Click "Save"
5. Your site will be available at `https://yourusername.github.io/pokemon-draft-league-replays/`

## Features

- Clean, responsive design
- Collapsible week sections
- Easy-to-update structure
- Mobile-friendly layout
- Pokemon-themed color scheme

## Customization

You can easily customize the appearance by editing `style.css`:
- Change colors by modifying the gradient values
- Adjust spacing and sizes
- Modify the layout grid

To change the title or season info, edit the `<header>` section in `index.html`.
