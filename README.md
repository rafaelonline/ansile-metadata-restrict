# EC2 Metadata Service restrict access

Prevents access to the instance metadata service using iptables rules.

The following example prevents access to the instance metadata service by all processes, except for processes running in the user account trustworthy-user.

```
iptables --append OUTPUT --proto tcp --destination 169.254.169.254 --match owner ! --uid-owner trustworthy-user --jump REJECT
```

## Requirements

Ansible v2.6+

## License

[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)

