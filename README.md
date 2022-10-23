# ts-events-emitter

A typesafe event emitter for TypeScript.

## Installation

```bash
npm install ts-events-emitter
```

## Usage

```ts
import eventsEmitter from "ts-events-emitter";

type TEvent = {
  "event-one": { a: number; b: string };
  "event-two": { c: number; d: string };
};

const emitter = eventsEmitter<TEvent>();

emitter.on("event", (event) => {
  console.log(event.a);
});

emitter.emit("event1", { foo: "bar" });
```

## Emitting events

```ts
emitter.emit("event-one", { a: 1, b: "foo" });
```

## Listening to events

```ts
emitter.on("event-one", (event) => {
  console.log(event.a);
});
```

## API

### `eventsEmitter`

#### `emit`

```ts
emit: <P extends keyof T>(event: P, message: T[P]) => void;
```

#### `on`

```ts
on: <P extends keyof T>(event: P, callback: (message: T[P]) => void) => void;
```

#### `once`

```ts
once: <P extends keyof T>(event: P,callback: (message: T[P]) => void) => void;
```

#### `off`

```ts
off: <P_2 extends keyof T>(event: P_2,callback: (message: T[P_2]) => void) => void;
```

#### `ofAll`

```ts
 offAll: (event: keyof T) => void;
```
