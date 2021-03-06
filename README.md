<h2>Motivation</h2>
<p>Using the same programming language on the client and the server opens opportunities to share code between them. E.g., URL, types, functions.</p>
<p>In this repo, my client is a react vite project, and the server is an express application; both are using typescript.</p> 
<p>Use this project as a boilerplate code for any typescript-based react \ express projects that share info.</p>



<h2>Installation</h2>
<ul>
<li>
Perform the following from root directory , client directory and server directory

```
npm i

```
</li>
<li>Make sure concurrently and ts-node (used for server) are installed globally</li>
</ul>
<h2>Usage</h2>
Invoke from the root project to run the server and the client. This is done using concurrently

```
npm run dev
```


<h2>Points of interest</h2>
<ul>
<li>change code in common cause hot reload in react vite project out of the box</li>
<li>The server typescript compiler does not accept code in common dir out of the box. --watch must be used

```json
    "dev": "nodemon --watch ./ --watch ../common ./src/index.ts",
```

</li>
<li>Code change in common directory outside of the server directory does not cause out-of-the-box server restart when using nodemon. Use rootDirs instead of rootDirin in tsconfig.json

```json
    "rootDirs": ["./src" , "../common/src"],
```

</li>
</ul>
Use rootDirs in tsConfig.json to tell the server typescript compiler to look also in common use nodemon --watch


<h2>Reference</h2>
I build this repo on top of the repo <a href='https://github.com/NathanKr/react-vite-express-typescript-setup'>react-vite-express-typescript-setup</a> and just add the shared code feature