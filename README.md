# Next-Blog

A study case to learn basics of NextJS and deploy at Vercel.

## Tech Stack

**Built-in:** 

* [NextJS](https://nextjs.org/)
* [TailwindCSS](https://tailwindcss.com/)
* [Remark](https://github.com/remarkjs/remark-html#readme)

## Run Locally

Clone the project

```bash
  git clone https://github.com/leoyassuda/next-blog.git
```

Go to the project directory

```bash
  cd next-blog
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run dev
```

Open in your brwoser

* [localhost](http://localhosr:3000)

## How it works

1. In `posts` folder at root, create your Markdown file.
2. Start with this metadata in header 
   ```
    ---
    title: 'A title sample'
    date: '2021-12-25'
    ---

    YOUR CONTENT ...
   ```
3. Using the dependecy remark, will read all files in posts folder and generate our pages and create all routes. The metadata is important to generate all links in the main page.

### Authors

* **Leo Yassuda** - *Initial work* - [Next-Blog](https://github.com/leoyassuda/next-blog) - Portifolio [leoyas.com](https://leoyas.com)