## Installing Linux WSL

1. Ensure this is WSL 2.  It seems to run into a lock problem
2. Installing using the standard apt-get install haskell-stack didn't work either.  Found a more direct install in https://docs.haskellstack.org/en/stable/install_and_upgrade/ which does work:

  `wget -qO- https://get.haskellstack.org/ | sh`

## Creating a project

First update the identity information in `~/.stack/config.yaml`

Then:

`stack new <project name> new-template`
