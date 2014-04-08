ali-oss
=======

aliyun OSS(open storage service) node client. generator friendly.

a node.js wrapper for [OSS restful api](http://imgs-storage.cdn.aliyuncs.com/help/oss/OSS_API_20131015.pdf?spm=5176.383663.5.23.AHDSVr&file=OSS_API_20131015.pdf)

## Install

```
npm install ali-oss
```

## Usage

### Init

init a oss client, need `accessKeyId`, `accessKeySecret` and `bucket`

```js
var OSS = require('ali-oss');
var client = OSS.create({
  accessKeyId: 'id',
  accessKeySecret: 'xxx',
  bucket: 'test'
});
```

options:

 - accessKeyId
 - accessKeySecret
 - [host]: default to `oss.aliyuncs.com:8080`
 - [timeout]: default to '10s'

### Methods

#### upload

```
yield* client.upload(file, name, options);
```

options:

 - **file**: can be filepath, fileContent, stream
 - **name**: object name in oss
 - **options**:
    - timeout: request timeout
    - headers: custom headers, checkout the doc

#### get

```
yield* client.get(name, path, options);
```

options:

- **name**: object name in oss
- **path**: can be filepath and stream
- **options**:
  - timeout
  - headers

#### remove

```
yield* client.remove(name, options);
```

options:

- **name**: object name in oss
- **options**:
  - timeout

## License

MIT
