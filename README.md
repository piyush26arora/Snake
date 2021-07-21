# Nostalgic Snake Game
:writing_hand: This is a **Snake Game Single Page Application** built using :
* VanillaJS (for functionality features like Creation and Removal of Snake length Elements in the game)
* HTML5 (for basic structure)
* CSS3 (for styling and making UI attractive)

:technologist: While working on this project I also used VS Code's various Extensions for my advantage and also enhanced my knowledge of these tools as a developer .

Some of these Extensions were :
* Live Server
* JS (ES6) snippets
* Bracket Pair Colorizer

:seedling: Anyone interested in programming (especially Web Development) should definitely try out these extensions , for a nice developer experience .

```javascript
       //function that deals with ALL the possible outcomes of the Snake
    function moveOutcomes() {
  
            //deals with snake hitting border and snake hitting self
      if ( (currentSnake[0] + width >= (width * width) && direction === width ) || //if snake hits bottom
           (currentSnake[0] % width === width -1 && direction === 1) ||            //if snake hits right wall
           (currentSnake[0] % width === 0 && direction === -1) ||                  //if snake hits left wall
           (currentSnake[0] - width < 0 && direction === -width) ||                //if snake hits the top
           squares[currentSnake[0] + direction].classList.contains('snake')  )       //if snake goes into itself
        {
            confirm('Want to relive your Nokia phone nostalgia? Mr. Snake was waiting for you....')
            return clearInterval(interval)              //this will clear the interval if any of the above happen
      }
  
            //ACTUAL MOVEMENT OF THE SNAKE
      const tail = currentSnake.pop()                           //removes last ite of the array and shows it
      squares[tail].classList.remove('snake')                          //removes class of snake from the TAIL
      currentSnake.unshift(currentSnake[0] + direction)             //gives direction to the head of the array
  
            //deals with snake getting apple
      if(squares[currentSnake[0]].classList.contains('apple')) {
        squares[currentSnake[0]].classList.remove('apple')
        squares[tail].classList.add('snake')
        currentSnake.push(tail)
        
        randomApple()
        
        score++
        scoreDisplay.textContent = score
        clearInterval(interval)
        intervalTime = intervalTime * speed
        interval = setInterval(moveOutcomes, intervalTime)     //recursive call for checking conditions each time
      }
      squares[currentSnake[0]].classList.add('snake')
    }
  



```

:hourglass_flowing_sand:  Lastly , I hope my application would be of some help to you all . 


```
Thank you , happy coding 
```

:milky_way: :)
