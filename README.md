<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Madden NFL Stats Tracker</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Madden NFL Stats Tracker</h1>
  </header>
  
  <main>
    <section id="team-stats">
      <h2>Team Stats</h2>
      <div id="team-stats-list"></div>
    </section>
    
    <section id="player-stats">
      <h2>Player Stats</h2>
      <div id="player-stats-list"></div>
    </section>
  </main>
  
  <footer>
    <p>&copy; 2025 Madden Stats Tracker</p>
  </footer>
  
  <script src="app.js"></script>
</body>
</html>
/* style.css */
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  text-align: center;
  color: #333;
}

header {
  background-color: #004c97;
  color: white;
  padding: 20px;
}

h1 {
  font-size: 2.5em;
}

h2 {
  font-size: 1.8em;
  margin-top: 20px;
}

section {
  padding: 20px;
}

#team-stats, #player-stats {
  background-color: #ffffff;
  border-radius: 8px;
  margin: 10px auto;
  width: 80%;
  max-width: 600px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}

footer {
  margin-top: 30px;
  background-color: #004c97;
  color: white;
  padding: 10px;
}
// app.js
const teams = [
  { name: "Dallas Cowboys", wins: 10, losses: 5 },
  { name: "New England Patriots", wins: 12, losses: 3 },
  { name: "Green Bay Packers", wins: 8, losses: 7 },
  { name: "Kansas City Chiefs", wins: 13, losses: 2 }
];

const players = [
  { name: "Patrick Mahomes", team: "Kansas City Chiefs", touchdowns: 35, yards: 4000 },
  { name: "Aaron Rodgers", team: "Green Bay Packers", touchdowns: 30, yards: 3800 },
  { name: "Dak Prescott", team: "Dallas Cowboys", touchdowns: 28, yards: 3300 },
  { name: "Cam Newton", team: "New England Patriots", touchdowns: 25, yards: 3200 }
];

function displayTeamStats() {
  const teamStatsList = document.getElementById('team-stats-list');
  teams.forEach(team => {
    const teamDiv = document.createElement('div');
    teamDiv.innerHTML = `<strong>${team.name}</strong>: ${team.wins} Wins, ${team.losses} Losses`;
    teamStatsList.appendChild(teamDiv);
  });
}

function displayPlayerStats() {
  const playerStatsList = document.getElementById('player-stats-list');
  players.forEach(player => {
    const playerDiv = document.createElement('div');
    playerDiv.innerHTML = `<strong>${player.name}</strong> (${player.team}) - ${player.touchdowns} TDs, ${player.yards} Yards`;
    playerStatsList.appendChild(playerDiv);
  });
}

displayTeamStats();
displayPlayerStats();

