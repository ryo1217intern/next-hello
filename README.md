# Next.JSを使ってHello Worldを行う。
## GitHubに乗せる
1. まずgit initを作業用ファイルに行う。
2. githubにpushする。
```zsh
git add "file name" #commitしたい変更をpushする。全て変更したい場合は"git add ."
git commit -m "commit message" #ローカルリポジトリに変更を登録する。この際メッセージはしっかり残すこと。
git remote add originan <URL> #git initしたファイルにremote add <URL>することによって毎回URLを指定してリモートリポジトリにpushする必要がなくなる。
git push origin master #ここで初めてリモートリポジトリにpushすることができる。
```
3. yarn create next-appをおこなう
```
yarn create-app
```
をすることによって現在いるディレクトリ内にNext.JS環境を作ることができる。
4. page.tsxが基本的な画面を表示しているので必要のないファイルを削除する。
5. page.tsxを次のように編集する。
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