# Open edX plugins

</hr>

## Requirements

* Python >= 3.6
* Tutor Open edX
* Docker: v18.06.0+
* Docker Compose: v1.22.0+
  
## Installation

**1. Install the latest stable release of Tutor from pip:**

```\
pip install "tutor[full]"
```

**2. Run:**

```\
tutor local quickstart
```

or, for dev

```\
tutor dev quickstart
```

## Apply Plugins

**1. Clone**

```\
git clone git@github.com:thasipablo/open-edX-plugins.git
```

```\
cd open-edX-plugins/plugins
```

**2. We start by creating the plugins root folder:**

```\
mkdir -p "$(tutor plugins printroot)"
```

Taking **user_rules** as example:

```\
copy user_rules.py "$(tutor plugins printroot)"
```

We can verify that the plugin is correctly detected by running:

```\
$ tutor plugins 

...
user_rules    (disabled)    /home/yourusername/.local/share/tutor-plugins/user_rules.py
...
```

**3. Our plugin is disabled, for now. To enable it, we run:**

```\
$ tutor plugins enable user_rules

...
Plugin user_rules enabled
Configuration saved to /home/yourusername/.local/share/tutor/config.yml
You should now re-generate your environment with `tutor config save`.
...
```

**4. You should now re-generate your environment with:**

```\
tutor config save
```

**5. Your new settings will be taken into account by restarting your platform:**

```\
tutor local restart
```

or, with:

```\
tutor dev restart
```

**6. Done**

## Resources

* Installing [Tutor](https://docs.tutor.overhang.io/install.html).

* Creating a [Tutor plugin](https://docs.tutor.overhang.io/tutorials/plugin.html).
