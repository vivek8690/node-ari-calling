# Asterisk ARI one to one calling with hold bridge

Install asterisk on your loacl/remote machine and make sure all required modules are loaded 

## Asterisk Configurations [http.conf]
```asterisk
[general]
enabled=yes
bindaddr=<Local/Remote IP>
bindport=8088
```

## Asterisk Configurations [ari.conf]

```asterisk
[general]
enabled = yes
pretty = yes

[<username>]
type = user
read_only = no
password = <anysecret>
```

## Asterisk Configurations [extensions.conf]

```asterisk
[<context_name>]       # in which all the extensions are registered 
extent => _XXXX,1,Noop()
same => n,Stasis(<app_name>)
same => n,Hangup()
```

## Installation

Clone repository locally and run ```npm install && node index.js```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
