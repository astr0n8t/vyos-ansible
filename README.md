# vyos-ansible

An Ansible role to idempotently configure a VyOS 1.4 Appliance

> [!CAUTION]
> You can lock yourself out of your VyOS install with this role.  It will provision exactly what you define.  I recommend testing before using this on any production systems.

> [!TIP]
> To see a good example of how I use this, please reference my custom [lab](https://github.com/lab-astr0rack-net/core): specifically [here](https://github.com/lab-astr0rack-net/core/blob/main/ansible/host_vars/vyos.yml)

## Motivations

The reason I created this is that the Ansible provider for VyOS hasn't been updated since VyOS 1 and lacks quite a few important modules.  Also, it lacks any way to remove config entries, it just knows how to add them, and (sometimes) update them.

This role simply takes a jinja2 template and produces the relevant config section with it.

This role deletes the relevant config section before applying the configuration.  This means that everytime you run the role, it will overwrite your config, but it also means that when it does this the output will be a 1 to 1 mapping of what you define in your Ansible variables.  This is helpful because you know that the config you define via the variables is the config that will always be applied.

## Contributing

I have defined in this role what I need for my use case. If you find that you need more, feel free to add to it (just a jinja2 template of VyOS commands that create the relevant config section).  Feel free to create a PR, I'd love to expand this!

## Contributors

- [@astr0n8t](https://github.com/astr0n8t)

