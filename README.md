# Next.JSを使ってHello Worldを行う。
## GitHubに乗せる
1. まずgit initを作業用ファイルに行う。
1. githubにpushする。
```zsh
git add "file name" #commitしたい変更をpushする。全て変更したい場合は"git add ."
git commit -m "commit message" #ローカルリポジトリに変更を登録する。この際メッセージはしっかり残すこと。
git remote add originan <URL> #git initしたファイルにremote add <URL>することによって毎回URLを指定してリモートリポジトリにpushする必要がなくなる。
git push origin master #ここで初めてリモートリポジトリにpushすることができる。
```
1. yarn create next-appをおこなう
```
yarn create-app
```
をすることによって現在いるディレクトリ内にNext.JS環境を作ることができる。

1. page.tsxが基本的な画面を表示しているので必要のないファイルを削除する。

1. page.tsxを次のように編集する。
``` page.tsx
export default function Home() {
  return (
    <main>
      <p>
        Hello World Next.JS
      </p>
    </main>
  );
};
```

1. TailwindCSSを使ってテキストを装飾する。

要素を真ん中にするには次のようにする。
```
className="h-screen w-screen flex justify-center items-center"
```

テキストのサイズを変更するには次のようにする。

```
className="text-8xl text-bold"
```

1. せっかくなのでcomponentsを使って表示する.
src/app内にcomponentsフォルダを作成しHello.tsxファイルをその中に作成する。
その中に次のようなコードを記述する.
```
import React from 'react'

const Hello = () => {
    return (
        <div className='h-screen w-screen flex justify-center items-center text-8xl text-bold'>
            Hello World with Next.JS
        </div>
    );
    };

    export default Hello;
```
この子コンポーネントを親コンポーネントであるpage.tsxに渡すにはpage.tsxを次のように変更する。
```page.tsx
import Hello from "./components/Hello";

export default function Home() {
  return (
    <main>
      <Hello />
    </main>
  );
};
```
これによってHelloWorldをコンポーネントを使用して表示することができた。