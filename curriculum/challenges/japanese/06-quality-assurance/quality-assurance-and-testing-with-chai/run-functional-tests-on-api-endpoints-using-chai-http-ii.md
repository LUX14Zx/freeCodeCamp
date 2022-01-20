---
id: 587d824f367417b2b2512c59
title: Chai-HTTPを使用して API エンドポイントで機能テストを実行するⅡ
challengeType: 2
forumTopicId: 301592
dashedName: run-functional-tests-on-api-endpoints-using-chai-http-ii
---

# --description--

注意点として、このプロジェクトは [Replit](https://replit.com/github/freeCodeCamp/boilerplate-mochachai) の始動プロジェクト、または [GitHub](https://github.com/freeCodeCamp/boilerplate-mochachai/) からクローンされたプロジェクトに基づいて構築されています。

# --instructions--

`tests/2_functional-tests.js` 内で、`'Test GET /hello with your name'` テスト (`// #2`) を変更し、レスポンスの `status` と `text` をアサートしてテストに合格させてください。

ルートに `?name=<your_name>` を追加して名前を URL クエリとして送信してください。 エンドポイントは `'hello <your_name>'` で応答します。

# --hints--

すべてのテストに合格する必要があります。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

`res.status` == 200 をテストする必要があります。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'equal');
      assert.equal(data.assertions[0].args[0], 'res.status');
      assert.equal(data.assertions[0].args[1], '200');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

`res.text` == `'hello <your_name>'` をテストする必要があります。

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.text');
      assert.match(data.assertions[1].args[1], /hello [\w\d_-]/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

# --solutions--

```js
/**
  Backend challenges don't need solutions, 
  because they would need to be tested against a full working project. 
  Please check our contributing guidelines to learn more.
*/
```