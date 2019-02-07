* Overall goals
  * Update minion to latest node
  * Make it easier to deploy iobio backend outside the U

* Approaches
  * Remove all websocket functionality (and binaryjs with it) and replace with
    local file proxy (fibridge).
    * This would be nice and clean. The issue is getting response streaming to
      work properly in browsers. You can theoretically use XHR streaming
      responses, but in practice you run into issues with things like CORS
      (not too hard to fix) and maximum connections per origin, which is
      usually around 6 (ie you can't have more than 6 connections to any given
      host, which would translate into 6 iobio commands for us).
  * Remove binaryjs, but replace it with our own websocket functionality for
    handling requests.
    * This is quite a bit of work, but probably the best long-term solution.
      It frees us from the cruft of HTTP, while also getting rid of binaryjs
      and letting us update node.
  * Rewrite minion from scratch
    * Advantages
      * All the same advantages as removing binaryjs above
      * Use a more performant language. I recommend go or Rust.
      * Rework the URI schema to be simpler
  * Keep all current functionality but replace binaryjs
    * Currently the binaryjs dependency is what's keeping us on node v0.10. It
      would be tricky to replace without breaking things.
