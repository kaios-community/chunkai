# Chunkai

[![CircleCI](https://circleci.com/gh/garredow/chunkai/tree/main.svg?style=svg)](https://circleci.com/gh/garredow/chunkai/tree/main)

Chunkai is a library for downloading large files on KaiOS.

## Install

```
npm install chunkai
```

## Usage

```js
import { Chunkai } from 'chunkai';

const chunkai = new Chunkai({
  chunkByteLimit: 1048576,
  storageName: 'sdcard',
  remoteFileUrl: 'https://traffic.libsyn.com/secure/syntax/Syntax_-_442.mp3?dest-id=532671',
  localFileUrl: 'syntax_442.mp3',
});

chunkai.onProgress = (progress) => console.log('progress', progress);
chunkai.onComplete = (progress) => console.log('complete', progress);
chunkai.onError = (err) => console.log('error', err);

chunkai.start();
```
