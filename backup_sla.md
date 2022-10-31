We have to backup only infromation that our ansible playbook can't restore.


So we will backup only InfluxDB (logs) and Database


In our case we don't have to make backups very frequently because we don't have sensitive data.


Let's imagine we have sensitive data. For example we have website that sells plane tickets.
Let's also assume that we have 100 sales in 15 minutes. 
And we can afford loose 30 minutes of our uptime and respectfully sales.

So RPO would be 10 minutes and RTO also 20 minutes.

We would also save last 3 backups so we could restore data that was 30 minutes ago in case someone somehow modifies database entries.

