# copybara-action

Runs [Copybara](https://github.com/google/copybara) in GitHub Actions

## Usage
Specify `wilmol/copybara-action@v1` as a `step` in your `workflow.yml` file, for example:
```
steps:
  - uses: actions/checkout@v1

  - uses: wilmol/copybara-action@v1
    with:
      git_name: wilmol
      git_email: willjoemolloy@gmail.com
      ssh_key: ${{ secrets.SSH_KEY }}
      ssh_known_hosts: ${{ secrets.KNOWN_HOSTS }}
```

__Note,__ internally the action runs docker (specifically [this image](https://hub.docker.com/r/sharelatex/copybara)) so the step must run on Linux.

## Arguments
| Input  | Description | Usage |
| :---:     |     :---:   |    :---:   |
| `git_name` | git config username, for authoring with Copybara | _required_ |
| `git_email` | git config email, for authoring with Copybara | _required_ |
| `ssh_key` | ssh public key, for authenticating with Copybara | _required_ |
| `ssh_known_hosts` | ssh known hosts file contents, for authenticating with Copybara | _required_ |
| `path` | `copy.bara.sky` file path | optional (defaults to repo root) |

See https://github.com/google/copybara for more details, specifically [Using Docker to build and run Copybara](https://github.com/google/copybara#using-docker-to-build-and-run-copybara). 
