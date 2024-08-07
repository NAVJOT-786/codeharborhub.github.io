---
id: api-middlewares
title: Next.js-API MiddleWares
sidebar_label: Next.js - API MiddleWares
sidebar_position: 2
tags: [Next.js API Routes ]
description: "In this section, you will learn about API routes in  NEXT ."
---

Next.js - API MiddleWares

API Routes in Next.JS have built-in middlewares which helps in parsing the incoming request.

Following are the middlewares

- req.cookies − cookies object contains the cookies sent by the request. Default value is {}.

- req.query − query object contains the query string. Default value is {}.

- req.body − query object contains the request body parsed using 'content-type'. Default value is null.

Let's create an example to demonstrate the same.

In this example, we are going to update an user.js in pages/api directory.

Let's update the nextjs project used in API Routes chapter.

Create user.js file in pages/api directory as following.

```
export default (req, res) => {
   res.statusCode = 200
   res.setHeader('Content-Type', 'application/json')
   res.end(JSON.stringify({ query: req.query }))
}
```
Start Next.js Server

Run the following command to start the server −.

```
npm run dev

> nextjs@1.0.0 dev D:\Node\nextjs
> next

ready - started server on http://localhost:3000
info  - Loaded env from D:\Node\nextjs\.env.local
event - compiled successfully
event - build page: /api/user
wait  - compiling...
event - compiled successfully
event - build page: /next/dist/pages/_error
wait  - compiling...
event - compiled successfully
```

## Verify Output

Open http://localhost:3000/api/user?counter=1 in a browser and you will see the following output.

``` {"query":{"counter":"1"}} ```


<BrowserWindow>
      <div style={{display:'flex',flexWrap:"wrap",justifyContent:"center",alignItems:"center"}}>
      <div style={{flex:"1 0 20rem",minHeight:"20rem"}} id="output">
      <p>app listen in 3000...</p>
      </div>
      <div style={{flex:"1 0 20rem",minHeight:"20rem"}}>
      <button onClick={()=>{
         let button_ele=document.getElementById("button_ele")
          button_ele.style.display="none"
          let output=document.getElementById("output")
          let p=document.createElement("p")
          p.textContent="GET /api/user?counter=1 "
          output.appendChild(p) 
          setTimeout(()=>{
          let fontend=document.getElementById("fontend")
          fontend.textContent= JSON.stringify({"query":{"counter":"1"}},null,2)
          },1500)
      }} id="button_ele">click to see the output</button>
      <pre id="fontend"></pre>
      </div>
      </div>
</BrowserWindow>