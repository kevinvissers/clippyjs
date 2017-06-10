# Clippy
> Add Clippy or his friends to any website for instant nostalgia.
This project is a fresh rewrite of [Clippy.JS](http://smore.com/clippy-js) in ES6.
([Read More](http://smore.com/clippy-js))    

## Demos

Please be patient for first load. It may take some time as agents are loaded one by one.

- [Simple JSFiddle](https://jsfiddle.net/pi0/rtw8p05k)
- [Agents Zoo](https://pi0.github.io/clippyjs/demo/index.html) 

![image](https://user-images.githubusercontent.com/5158436/27002340-c221cc06-4df4-11e7-9438-050a3ad8ecde.png)


## Quick Setup

### Browser
Add this code to you to your page to enable Clippy2.

```html
<!-- Add the stylesheet to the head -->
<link rel="stylesheet" type="text/css" href="https://gitcdn.xyz/repo/pi0/clippyjs/master/assets/clippy.css" media="all">

<!-- Add these scripts to  the bottom of the page -->
<script src="https://unpkg.com/jquery@3.2.1"></script>
<script src="https://unpkg.com/clippyjs@latest"></script>
<script type="text/javascript">
clippy.load('Merlin', function(agent){
    // Do anything with the loaded agent
    agent.show();
});
</script>
```

### NPM / Webpack
Install dependency
```bash
yarn add clippyjs # or npm install clippyjs
```

Import and load
```js
import clippy from 'clippyjs'

clippy.load('Merlin', (agent) => {
    // do anything with the loaded agent
    agent.show();
});
```
## Actions
All the agent actions are queued and executed by order, so you could stack them.

```javascript
// play a given animation
agent.play('Searching');

// play a random animation
agent.animate();

// get a list of all the animations
agent.animations();
// => ["MoveLeft", "Congratulate", "Hide", "Pleased", "Acknowledge", ...]

// Show text balloon
agent.speak('When all else fails, bind some paper together. My name is Clippy.');

// move to the given point, use animation if available
agent.moveTo(100,100);

// gesture at a given point (if gesture animation is available)
agent.gestureAt(200,200);

// stop the current action in the queue
agent.stopCurrent();

// stop all actions in the queue and go back to idle mode
agent.stop();
```

## Custom CDN / Agents
By default all agents are being served from GitHub CDN (this repo) in order to customize loading base path, 
Use 4rd argument of `load` function. (**path should end with slash /**)
```js
clippy.load('Marline', function() {
  
}, undefined, './agents/')
```

# Licence
MIT

## Special Thanks
- The [Clippy.JS](http://smore.com/clippy-js) project by [Smore](http://smore.com)
- The awesome [Cinnamon Software](http://www.cinnamonsoftware.com/) for developing [Double Agent](http://doubleagent.sourceforge.net/)
the program we used to unpack Clippy and his friends!
- Microsoft, for creating clippy :)