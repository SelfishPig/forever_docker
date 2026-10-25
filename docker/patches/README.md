# Patches applied to TrinityCore (forever branch)

Applied in name order right after the `git clone` (see the Dockerfile). The build stops if a patch no longer
applies: either it was merged into the branch (delete it) or it needs updating.

| File | What it fixes (found with packet logs of client 1.60.1.70450) |
|---|---|
| `0002-classic-surname-names.patch` | The 1.60 client shows and sends "Name Surname". `normalizePlayerName` keeps the first word only (add friend, ignore, guild, mail by name: no more "player not found"). |
| `0003-classic-contact-list-request.patch` | The 1.60 client's `CMSG_SEND_CONTACT_LIST` is 5 bytes: one byte (0) before the flags. Read as a uint32 it gave wrong flags (0x1500) and the server sent an empty friend list every time it was opened, although the friends were stored. |
