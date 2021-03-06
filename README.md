## What is this about?

What started out as a simple way to show how to mass block the sun and all that is evil about them, has quickly turned into a 'how do we block all who use the Internet to spread hatred and lies?'

This is about the infrastructure these publications use to spread their hate. The Domain Name System (DNS) and complex Content Delivery Networks (CDNs) that host and serve.

![dailymail](img/dailymail.png)

As time permits, I'll continue to map and explore their vast networks so you can use the info to block them as you see fit.

### Online presence

![thesun](img/thesun-web.jpg)

This is how The Sun newspaper looks on the Internet. Too often, the main domain name isn't the only entity, todays websites consists of many different sub-domains. In order to not see the content they serve, you need to understand all the pieces that make up the puzzle.

![The_Sun_Liverpool](img/The_Sun_Liverpool.jpg)

For more information as to why, [this](https://www.vice.com/en_uk/article/gyzmzb/boycott-the-sun-ban-merseyside-uk) should help.

### Which publications do you currently have mapped?

- The Sun https://thesun.co.uk
- The Daily Mail https://dailymail.co.uk
- The Daily Express https://dailyexpress.co.uk
- The Telegraph https://telegraph.co.uk

### How do you use this information?

You can either import the CSV files into Pi-Hole, which is a great project to blackhole Internet advertisments, or you can manually edit your hosts file. This is simpler than you think, just follow these steps:

#### Microsoft Windows 10

1. The file you want to download is `megahostsfile.txt`, so save this somewhere easily accessible

2. Using the search function, search for Notepad.exe. On the right, you'll see 'Run As Administrator', click this

   ![notepad1](img/notepad1.png)

3. The hosts file is located at `C:\**Windows**\System32\drivers\etc\**hosts**`, in Notepad, go to file --> open and navigate to that location. It should look like this

![hostsfile](img/hostsfile.png)

4. Now go back to where you saved the `megahostsfile.txt` and double-click on it. It should open up in Notepad. Copy the entire file.

5. In the other Notepad window, you want to paste the contents of `megahostsfile.txt` into it and save it.  

What used to look like

![thesunhomepage](img/thesunhomepage.png)

Will now look like

![thesunhomepagenomore](img/thesunhomepagenomore.png)


Under Mac OS X, follow this [guide](https://www.hostinger.co.uk/tutorials/how-to-edit-hosts-file-macos)

### Using these blocklists with [Pi Hole](https://pi-hole.net/)

[Pi Hole](https://pi-hole.net/) is a network-wide Ad blocker for the [Raspberry Pi](https://www.raspberrypi.org/). You can use these lists with the Pi Hole quite easily.

In your Pi Hole Admin Panel (http://yourpihole/admin) browse to _Settings_ and then _Blocklists_ (see below). Then in the text box which states "_Enter One URL per line to add new blocklists_" add your disired blocklists, separated by a carrage return, before clicking the _Save and Update_ button. You will need to use the `$name__web.csv` files with Pi Hole. For example to block The Daily Express, The Daily Mail, The Telegraph and The Sun you would enter:

`https://raw.githubusercontent.com/danielcuthbert/thescum/master/dailyexpress_web.csv`
`https://raw.githubusercontent.com/danielcuthbert/thescum/master/dailymail_web.csv`
`https://raw.githubusercontent.com/danielcuthbert/thescum/master/telegraph_web.csv`
`https://raw.githubusercontent.com/danielcuthbert/thescum/master/thesun_web.csv`

This should result in the blocklists now appearing in your Pi Hole Blocklist settings as follows:

![Pi Hole Settings](img/pihole-bl-settings-blr.png)

### Advanced usage

Sites like this need the support of the global ad and pervasive tracking network. In order to understand who support them, I've started to map who their partners are and this information can be found in the `$name_ips_expanded.csv` file. It's more of a work in progress.
