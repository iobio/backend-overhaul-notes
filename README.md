# Potential Feature List

* Simplicity
  * Monolith?
    * Dedicated endpoints
  * Replace local file support with proxy ([fibridge](https://github.com/anderspitman/fibridge-proxy-js))
  * Replace multi-input support with [process substitution](http://tldp.org/LDP/abs/html/process-sub.html)
    or at least a separate wrapper ([argurl](https://github.com/anderspitman/argurl))
  * Run on developer laptop if possible
* Better instrumentation
  * Error reporting
  * Performance
* Write in Go?
  * Easier deployment (static binaries)
  * Potential performance
  * Type safety
* Flow control/backpressure
* Canceling streams
