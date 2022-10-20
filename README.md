# cluster-script-types (Unofficial)

🤖 a Unofficial [Cluster Script](https://docs.cluster.mu/script/index.html) type definitions for [TypeScript](https://www.typescriptlang.org/).

(非公式な Cluster Script の TypeScript 向け型定義です)

> **MEMO:** This project is unofficial and intended for personal use. And is a work in progress and may be missing some types of information. Type information is based on official documentation.
> 
> **メモ:** このプロジェクトは非公式であり個人利用を想定しています。また、進行中でありいくつかの型情報が不十分な場合があります。型の情報は公式のドキュメントをもとにしています。

## Getting started / はじめかた

1. Copy the type definition file `cluster.d.ts` to your project.
    - `cluster.d.ts` をあなたのプロジェクトにコピーします
2. Use `tsconfig.json` or [Triple-Slash Directives](https://www.typescriptlang.org/docs/handbook/triple-slash-directives.html) to reference type information.
    - `tsconfig.json` や Triple-Slash Directives を使用して型情報を参照してください

## Sample / サンプル

```js
/// <reference path="./cluster.d.ts" />

const cube = $.subNode('Cube')
const axis = new Vector3(0.33, 0.66, 1)

$.onUpdate((deltaTime) => {
  /** @type number */
  const time = ($.state.time ?? 0) + deltaTime
  $.state.time = time
  const rot = new Quaternion().setFromAxisAngle(axis, (time % 360) * 255)
  cube.setRotation(rot)
})
```
