# Islandora Updater

A shell script to update all repositories in a Drupal setup.

## Installation

Pull this directory, ensure that all the modules you want to use are listed in the islandora-modules-sans-tuque.txt file. If a module is listed but does not exist on the filesystem it will be skipped. Assumes that **Islandora** == **origin**.

## Usage
```
> ./update -h
Usage update: (-p | -f | -b <branch>)
  -p            : pull new updates to the current branch
  -f            : fetches updates and new branches
  -b (<branch>) : list branches or check out <branch>
  -a <file>     : archive current commits to file <file>
  -r <file>     : revert to commits in backup <file>
```

This script is generally meant to be used in the context of [islandora_vagrant](https://github.com/Islandora-Labs/islandora_vagrant.git). It assumes that the remote **origin** is the Islandora remote. It cycles through all the files in the **islandora-modules-sans-tuque.txt** and executes the command you specified.

## Configuration

Inside the **update** script you can alter two variables.

**NOTE**: Both of these variables use the file path **inside** the vagrant machine.

```
BASE_DIR="/var/www/drupal/sites/all/modules"
```
where the Drupal module directory is.

```
MODULE_FILE="/vagrant/islandora-module-list-sans-tuque.txt"
```
where the file of Islandora modules to act on is.


## Maintainers

* [Jared Whiklo](https://github.com/whikloj)

## License

* MIT

