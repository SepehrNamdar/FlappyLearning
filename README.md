# Flappy Learning ([Demo](http://xviniette.github.io/FlappyLearning/))

Program that learns to play Flappy Bird by machine learning ([Neuroevolution](http://www.scholarpedia.org/article/Neuroevolution))

![alt tag](https://github.com/xviniette/FlappyLearning/blob/gh-pages/img/flappy.png?raw=true)

### Demo controls

Open `index.html` in a browser. Use x1, x2, x3, x5 or MAX to select the simulation speed.

Use **Pause** to freeze the simulation and learning, including at MAX speed. **Resume** continues from the same state without restarting or catching up elapsed time. Speed controls remain usable while paused; the selected speed applies on resume.

The Pause/Resume button becomes available when the sprites finish loading. Reach it with Tab (with a visible focus outline) and activate it with Enter or Space.

### [NeuroEvolution.js](http://github.com/xviniette/FlappyLearning/blob/gh-pages/Neuroevolution.js) : Utilization
```javascript
// Initialize
var ne = new Neuroevolution({options});

//Default options values
var options = {
    network:[1, [1], 1],    // Perceptron structure
    population:50,          // Population by generation
    elitism:0.2,            // Best networks kepts unchanged for the next generation (rate)
    randomBehaviour:0.2,    // New random networks for the next generation (rate)
    mutationRate:0.1,       // Mutation rate on the weights of synapses
    mutationRange:0.5,      // Interval of the mutation changes on the synapse weight
    historic:0,             // Latest generations saved
    lowHistoric:false,      // Only save score (not the network)
    scoreSort:-1,           // Sort order (-1 = desc, 1 = asc)
    nbChild:1               // number of child by breeding
}

//Update options at any time
ne.set({options});

// Generate first or next generation
var generation = ne.nextGeneration();

//When an network is over -> save this score
ne.networkScore(generation[x], <score = 0>);
```

You can see the NeuroEvolution integration in Flappy Bird in [Game.js](http://github.com/xviniette/FlappyLearning/blob/gh-pages/game.js).
