### > Smoke out the Rat challenge :

# > Description :

> There was a major heist at the local bank. Initial findings suggest that an intruder from within the bank, specifically someone from the bank's database maintenance team, aided in the robbery. This traitor granted access to an outsider, who orchestrated the generation of fake transactions and the depletion of our valuable customers' accounts. We have the phone number, '789-012-3456', from which the login was detected, which manipulated the bank's employee data. Additionally, it's noteworthy that this intruder attempted to add gibberish to the binlog and ultimately dropped the entire database at the end of the heist.

> Your task is to identify the first name of the traitor, the last name of the outsider, and the time at which the outsider was added to the database.

> Flag format : VishwaCTF{TraitorFirstName_OutsiderLastName_HH:MM:SS}

We received the DBlog-bin.000007 file as an attachment.

To retrieve the information, we used the strings command on the file, which provided us with the bank's database.

The challenge description instructed us to find the first name of the traitor with the phone number 789-012-3456.

Through a simple search, we identified the traitor as Matthew Williams.

![](https://cdn.discordapp.com/attachments/1067452256686981161/1213918977999241286/Screen_Shot_2024-03-03_at_7.40.28_PM.png?ex=65f73925&is=65e4c425&hm=cc785bf0c3d9b7f56abdad8c3317f44aff5bb29dc83c233bff080c4bbcbc6bfb&)

Now, moving on to the outsider who is part of the maintenance team:

Within the database, we found a table of maintainers containing only one person, named John.

![](https://cdn.discordapp.com/attachments/1067452256686981161/1213918110940270652/Screen_Shot_2024-03-03_at_7.36.58_PM.png?ex=65f73857&is=65e4c357&hm=1a89dd0e4e96b52d6b6ad767b64ad91e2a7b2f2c91be42625563481da472109f&)

To proceed, we need to determine John's last name, so we performed a search for his name.

![](https://cdn.discordapp.com/attachments/1067452256686981161/1213919678003552387/Screen_Shot_2024-03-03_at_7.43.15_PM.png?ex=65f739cc&is=65e4c4cc&hm=32f90a81ac164cf83fc70d4414d22f160618a279bed8091f69a6bf03259801b6&)

for timestamp you must convert it to IST (Indian Standard Time).

FLAG : 
> VishwaCTF{Matthew_Darwin_15:31:29}
