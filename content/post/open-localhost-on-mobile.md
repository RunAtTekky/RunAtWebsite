+++
title = 'Open Localhost on Mobile'
date = 2025-08-23T21:58:41+05:30
draft = false
+++
While developing websites, you must have tried to make your website responsive.
For checking how your website looks on your phone, you must have used `toggle device toolbar` or resized the window after pressing `F12`.

But on actual phone browser you have top and bottom bars which causes the website to look and feel drastically different than the one you see on your laptop by `toggling device toolbar`.

What if there was a simple way of opening the `localhost` on your mobile device.
Today we will learn how to do that.

## Solution
Run your application server on `localhost:port`
You can do this however you want. I'm using `live-server` program which I installed using `npm`.

Run the program and it will `serve` your website on `localhost:port`.
For me this was `localhost:8080`.

What we need to do is connect to our computer's `IP address`.

Run the following command if you are on linux, I don't know about windows.
```bash
ip address | grep "inet " | grep -v 127.0.0.1
```

Output:
```bash
inet XXX.XX.XXX.XXX/XX brd XXX.XX.XXX.XXX scope global dynamic noprefixroute wlpXsX

inet XXX.XX.XXX.XXX/XX metric XXX brd XXX.XX.XXX.XXX scope global secondary dynamic wlpXsX

inet XXX.XX.X.X/XX brd XXX.XX.XXX.XXX scope global docker0

inet XXX.XX.X.X/XX brd XXX.XX.XXX.XXX scope global br-cc719d570f98
```

If your firewall is blocking incoming connections to port (say 8080) run the following command
```bash
sudo ufw allow 8080/tcp
```

The first two `IPs` in the output are useful. On your mobile device try running the following on a browser.

> Note that your computer and mobile device need to be on the same network.

```bash
XXX.XX.XXX.XXX:PORT
172.25.261.143:8080 (example)

orthesecondIP:PORT
```

This would run the localhost on your phone.

Now you can easily see how your website will look on the phone.

