# Install core

    # Install ependencies.
    sudo apt install curl git

    # Core installation.
    git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.15.0
    
    # Add the following to ~/.bashrc:
    . "$HOME/.asdf/asdf.sh"
    . "$HOME/.asdf/completions/asdf.bash"

    # Evaluate startup file.
    source ~/.bashrc

# List tool plugins

- all available:

        asdf plugin list all

- installed:

        asdf plugin list
        asdf plugin list --urls

# Install tool plugin

        asdf plugin add <tool> <git-url>
        asdf plugin add elixir https://github.com/asdf-vm/asdf-elixir.git

# List tool versions

- all available:

        asdf list all <tool>
        asdf list all elixir

- all installed:

        asdf list

- specific installed:

        asdf list <tool>
        asdf list elixir

- all currently used:

        asdf current

- specific currently used:

        asdf current <tool>
        asdf current elixir

- show latest stable version:

        asdf latest <tool>
        asdf latest <tool> <version>

# Install tool version

- specific version:

        asdf install <tool> <version>
        asdf install elixir 1.16.1
    
- latest specific version:

        asdf install <tool> latest<:version>
        asdf install elixir latest:1.16

- all tools with version specified in the `.tool-version` file:

        asdf install

- specific tool with version specified in the `.tool-version` file:

        asdf install <tool>

# Set tool version

- local:

        asdf local <tool> <version>
        asdf local <tool> latest<:version>

- global:

        asdf global <tool> <version>
        asdf global <tool> latest<:version>

- shell (for current shell session):

        asdf shell <tool> <version>

# Helpful utils

- display real path to executable:

        asdf which <tool>

    > NOTE:  
    System's `which` displays path to `asdf`'s shim instead of executable,
    e.g.:  
    `which elixir` displays `~/.asdf/shims/elixir`  
    `asdf which elixir` displays `~/.asdf/installs/elixir/1.16/bin/elixir`
