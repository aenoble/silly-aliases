# Silly Aliases

A collection of simple, short aliases to be added to your shell config of
choice.

## dadjoke
Prints a joke to stdout
```bash
alias dadjoke="curl -sH \"Accept: application/json\" https://icanhazdadjoke.com/ | cat | python -c \"from json import loads;from sys
import stdin; print(loads(stdin.read())['joke'])\""
```

## nettest
ping google's DNS.  If it's not returning packets it's *highly likely* you're
having a local network outage.
```bash
alias nettest="ping -a 8.8.8.8"
```