# delayquery

chainable when &amp;&amp; jQuery

```
// copy(Object.keys(optimizely.$.fn))
var keys = ["constructor", "init", "selector", "jquery", "length", "size", "toArray", "get", "pushStack", "each", "ready", "eq", "first", "last", "slice", "map", "end", "push", "sort", "splice", "extend", "data", "removeData", "queue", "dequeue", "delay", "clearQueue", "promise", "attr", "removeAttr", "prop", "removeProp", "addClass", "removeClass", "toggleClass", "hasClass", "val", "bind", "one", "unbind", "delegate", "undelegate", "trigger", "triggerHandler", "toggle", "hover", "live", "die", "blur", "focus", "focusin", "focusout", "load", "resize", "scroll", "unload", "click", "dblclick", "mousedown", "mouseup", "mousemove", "mouseover", "mouseout", "mouseenter", "mouseleave", "change", "select", "submit", "keydown", "keypress", "keyup", "error", "find", "has", "not", "filter", "is", "closest", "index", "add", "andSelf", "parent", "parents", "parentsUntil", "next", "prev", "nextAll", "prevAll", "nextUntil", "prevUntil", "siblings", "children", "contents", "text", "wrapAll", "wrapInner", "wrap", "unwrap", "append", "prepend", "before", "after", "remove", "empty", "clone", "html", "replaceWith", "detach", "domManip", "appendTo", "prependTo", "insertBefore", "insertAfter", "replaceAll", "css", "Va", "conditionalRemove"]

var methodFactory = (type) => {
  return function (...args) {
    this._queue = this._queue || [];
    if (type === null) {
      // start a new chain array
      this._queue.push([[type, ...args]]);
    } else {
      // push to old chain array
      this._queue.last().append([type, ...args]); // i suck at arrays
    }
    return this;
  };
};

var $dq = methodFactory(null);

keys.forEach((key)=> {
  $dq[methods[i]] = methodFactory(methods[i]);
});

pollForjQuery.then(flushQueue); // psuedocode

$dq('selector').text('string').html('again').css('border', 'solid 1px red');
```
