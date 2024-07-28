---
theme: ./
layout: cover
---

# Slidev Theme Starter

Presentation slides for developers

<div class="pt-12">
  <span @click="next" class="px-2 p-1 rounded cursor-pointer hover:bg-white hover:bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

---
layout: section
subject: What is Slidev?
---

---
layout: default
headerEnable: true
headerTitle: What is Slidev?
headerLogo: https://sli.dev/logo.svg
---

# What is Slidev?

Slidev is a slides maker and presenter designed for developers, consist of the following features

- 📝 **Text-based** - focus on the content <strong class="accent">with</strong> <strong class="danger">Markdown</strong>, and then style them later
- 🎨 **Themable** - theme can be shared and used with npm packages
- 🧑‍💻 **Developer Friendly** - code highlighting, live coding with autocompletion
- 🤹 **Interactive** - embedding Vue components to enhance your expressions
- 🎥 **Recording** - built-in recording and camera view
- 📤 **Portable** - export into PDF, PNGs, or even a hostable SPA
- 🛠 **Hackable** - anything possible on a webpage

<br>
<br>

- - -

Read more about [Why Slidev?](https://sli.dev/guide/why)

---
layout: center
headerEnable: true
headerTitle: What is Slidev?
---

# Slidev

Slidev is a slides maker and presenter designed for developers, consist of the following features

Read more about [Why Slidev?](https://sli.dev/guide/why)

---
headerEnable: true
headerTitle: What is Slidev?
colorSchema: light
---

# Navigation

Hover on the bottom-left corner to see the navigation's controls panel

## Keyboard Shortcuts

|     |     |
| --- | --- |
| <kbd>space</kbd> / <kbd>tab</kbd> / <kbd>right</kbd> | next animation or slide |
| <kbd>left</kbd>  / <kbd>shift</kbd><kbd>space</kbd> | previous animation or slide |
| <kbd>up</kbd> | previous slide |
| <kbd>down</kbd> | next slide |

---
layout: two-cols
headerEnable: true
headerTitle: What is Slidev?
image: https://cover.sli.dev
---

# Two Columns

Left and right content layout

::left::

```ts
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

::right::

```ts
interface Post {
  id: number
  title: string
  content: string
}

function updatePost(id: number, update: Partial<Post>) {
  const post = getPost(id)
  const newPost = { ...post, ...update }
  savePost(id, newPost)
}
```

---
layout: image-right
headerEnable: true
headerTitle: What is Slidev?
image: https://cover.sli.dev
---

# Image Right

Right content layout with image on the left

```ts
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

---
layout: image-left
headerEnable: true
headerTitle: What is Slidev?
image: https://cover.sli.dev
---

# Image Left

Left content layout with image on the right

```ts
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

---
layout: image
headerEnable: true
headerTitle: What is Slidev?
image: https://cover.sli.dev
---

# Image

Full-width image layout

```ts
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

---
layout: center
---

# Learn More

[Documentations](https://sli.dev) / [GitHub Repo](https://github.com/slidevjs/slidev)
