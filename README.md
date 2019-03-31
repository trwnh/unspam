# unspam
lazy python script to block ips that generate spammy nginx log lines

## usage
edit your keywords and then run the script

- `unspam <access-log>` will filter log lines based on the dictionary currently defined in spammy().
- `unspam -b <access-log>` or `unspam -ban <access-log>` will do the same, but also pass the discovered spammy IPs to a custom `ipban` bash script i wrote, which is a thin wrapper around `sudo ufw deny from @IP`

outputs two files with trimmed log files that include only ip, request, and response:
- `spammy.txt` is a list of detected spam lines
- `clean.txt` is a list of lines not detected as spam

maybe in the future i'll expand on this script to be able to use external dictionaries but really i just wrote this so my nginx log files wouldn't grow too quickly ✌️

## etc
contact me if you've got any questions:
a@trwnh.com (email/xmpp)
[mastodon.social/@trwnh](https://mastodon.social/@trwnh) (activitypub)
[trwnh.com](https://trwnh.com) (homepage)

also if you find yourself unable to load any of my sites, then let me know because i may have used some overly broad dictionary rules while testing this :x
