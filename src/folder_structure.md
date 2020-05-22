# Folder Structure

Even though you can put everying in a single text file with Beancount, I've found it useful to split things up into a couple text files.

**We're not going to worry about tracking finances since the beginning of time. That's like cleaning out an email inbox with thousands of unread messages. Too daunting.** Just _starting_ is what's important. Start with the current month and don't worry about what happened before.

Start by making a folder somewhere on your computer. I call mine `finances`. Put a file in this folder and call it `main.bean`. It's okay that this file is empty for now.

Make a folder inside your `finances` folder named after the four-digit year. As I write, this is `2020`.

Make a folder for each month inside your `2020` folder. The name of the folder should be the two-digit number of the month. May would be `05`.

Think a little bit about the major sources of money in/out in your life. I have a Chase credit card and Wells Fargo checking and savings accounts. Inside my `05` folder, I'll make three text files: one for each account. Don't stress about getting this "right". You can always change it later and use one text file inside `05` for now.

---
When you save text files inside VS Code, save them as `.bean` files. This will help other programs know they're text files being used with Beancount.

---

Make a file called `includes.bean` inside your `2020` folder. It can be empty for now.

Here's what my `finances` folder looks like:
```
.
├── 2020
│   ├── 05
│   │   ├── cc_chase.bean
│   │   ├── wf_checking.bean
│   │   └── wf_savings.bean
│   └── includes.bean
└── main.bean
```

Open your `finances` folder and run:
```
bean-check main.bean
```
You shouldn't see any output but should also not see any error.

In the next section, we'll "bring to life" this folder structure by creating accounts.