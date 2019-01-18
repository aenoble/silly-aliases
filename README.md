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

## let_me_in
Delete a line from your ~/.ssh/known_hosts file when you get yelled at.
Must pass in an argument.
```
let_me_in () {
  sed -i -e '$1d' ~/.ssh/known_hosts
}
```

*Usage:* `let_me_in 102`

## docker_ips
Lists local ips of running docker containers.
```
docker ps | awk '{print $1}' | tail -n +2 | xargs docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}'
```

## shrug
Copies the shrug guy thing into my clipboard.
```
shrug() { echo "¯\_(ツ)_/¯" | pbcopy }
```

## longfiles
Lists line counts of files in ascending order
```
find . -name '*' | xargs wc -l | sort -n
```
