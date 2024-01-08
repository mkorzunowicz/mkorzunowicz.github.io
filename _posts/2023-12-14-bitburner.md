---
layout: post
title:  "Bitburner"
date:   2023-12-15 13:37:00 +0100
categories: [games]
tags: [javascript, games, logical, scripting]
---

## Summary

Some time ago I found a game, which absorbed me intensely. It's Bitburner and it's free! You can play it on [Steam](https://store.steampowered.com/app/1812820/Bitburner/) or in a [browser](https://bitburner-official.github.io/). You become a hacker and your job is to (obviously) hack servers.. but not only - you can run a corporation, chase androids, infiltrate companies, commit crime.. there's plenty to do. The genre is "idle", but a lot must be done actively to learn the ropes. You unlock additional functionalities when hacking through different Nodes. And there's plenty of achievements.. I love chasing achievements even if I sometimes cheat :P

### Javascript

The cool stuff about this game is that, in the recent version of it, you program in JavaScript. Not that I managed to gain some amazing programming skills thanks to it, but the relatively quick feedback loop of "code some, see the result" gives quite a bit of satisfaction. The game is made in React so whether in Browser or as an app in Electron, you can open the Debug window. And you probably should too! There's much to explore there as there are some hidden quirks about the game itself, but it will also help you not fall into an endless loop when writing your scripts.

 So I was lost for long hours when coding looped infiltrations, installing Augmentations, hacking shitloads of servers (obviuosly in an automated way, by scanning them and then attacking) and what not. To literrally observe how it plays itself, left for long hours grinidng :D The kind of idle I like, since I'm the one who automated it. The scripts I wrote are probably far from being optimal, but that's not what this is about. It's no leetCode ;) Anyway, totally recommended. Spoilers alert - the scripts I wrote for it are on my [GitHub](https://github.com/mkorzunowicz/bitburner-scripts). Of course they kinda evolved as new functionalities were enabled, so not all of it will work right away. And besides.. what fun would it be to have the solutions before you even start.

### The Cave

A little snippet from my code.

```javascript
if (ns.getHackingLevel() > ns.getServerRequiredHackingLevel(target) && ns.singularity.getOwnedAugmentations().includes('The Red Pill')) {
      if (numberOfPortsOpenable(ns) < 5) {
        log(ns, `Couldn't crack ports on w0r1d_d43m0n`, 'warning', 1000 * 30);
        return;
      }

      log(ns, `Killed BITNODE ${ns.getResetInfo().currentNode} and starting next on ${next} ${timeSinceBitNodeReset(ns)}`, 'warning', 1000 * 60 * 30, true);
      ns.singularity.destroyW0r1dD43m0n(next, 'starter.js');
}
```

![Bitburner corporation](/assets/img/bitburner-corpo.png)
