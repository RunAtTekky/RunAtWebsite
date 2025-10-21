# RunAt's Blog
This is where I will share:
- New things I learn
- Updates about my life

# Inspiration
This blog was inspired by [Luke Smith](https://lukesmith.xyz/)

I was very heavily inspired by this website
[based.cooking](https://based.cooking/)

Watched this video to learn about HUGO
[Luke Smith HUGO Tutorial](https://youtu.be/ZFL09qhKi5I)

# How to setup
Clone the repo
```bash
git clone https://github.com/RunAtTekky/RunAtWebsite.git
```

Clone the submodules: the themes you are using
```bash
git submodule update --init --recursive
```

Check if you have hugo installed
```bash
hugo version
# You must get some output like this
hugo v0.151.2+extended+withdeploy linux/amd64 BuildDate=unknown
```

If you don't get this output, you must first install hugo.

On arch (using yay or paru)
```bash
yay -S hugo
# or
paru -S hugo
```

To run the website
```bash
hugo server --noHTTPCache
```

Now go to the localhost:PORT specified in the output, usually it is localhost:1313, to view the website.
