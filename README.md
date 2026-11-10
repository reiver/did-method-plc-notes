# did-method-plc Notes

[plc.directory](https://plc.directory) is a key part of DID-PLC.

DID-PLC is a popular DID method used on the ATProto ATmosphere — which includes Bluesky, Blacksky, Leaflet, and others.

The source-code for [plc.directory](https://plc.directory) open-source, and available here:

* https://github.com/did-method-plc/did-method-plc

## Running plc.directory Locally

If you are a computer-programmer working with ATProto, then you may want to run your own local alternative to [plc.directory](https://plc.directory)

Here are the steps to do that.

### Step 1: clone the git repository

```
git clone https://github.com/did-method-plc/did-method-plc.git
```

### Step 2: install dependencies

```
pnpm install --pm-on-fail=ignore
```

### Step 3: build

```
pnpm --pm-on-fail=ignore build
```

### Step 4

### Step 5: run server

```
pnpm --pm-on-fail=ignore start
```
