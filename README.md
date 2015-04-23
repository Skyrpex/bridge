Bridge
======

Provides a communication channel between pages and iframe elements.

## Installation

```
npm install @skyrpex/bridge --save
```

## Usage

### On the host page:

```javascript
import Bridge from "@skyrpex/bridge";
let bridge = new Bridge();
bridge.guest("myName", { url: "guest.html" }).then(guest => {
	guest.set("html", "<h1>Hello from host!</h1>");
});
```

### On the guest page:

```javascript
import Bridge from "@skyrpex/bridge";
let bridge = new Bridge();
bridge.host().then(host => {
	host.observe("html", html => console.log(`HTML received: ${html}`));
});
```
