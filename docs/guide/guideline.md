---
title: วิธีติดตั้ง Golang
meta:
  - name: วิธีติดตั้ง Golang
  - content: วิธีติดตั้ง Golang
---

#  วิธีติดตั้ง `GOPATH`
การติดตั้ง `GOPATH` จะทำให้เราสามารถ compile เเละนำมา dev  ในเครื่องสะดวกมากขึ้น หากไม่กำหนด PATH `GOPATH` ระบบจะติดตั้ง PATH ซึ่งเป็น default ให้ตามนี้
 - `$HOME/go`  บน  Unix
 - `%USERPROFILE%\go`  บน windows

โดยสารมารถติดตั้งเพิ่มเติมได้ดังนี้ ซึ่งวิธีจะต่างกันไปตาม Terminal ที่เเต่ล่ะคนใช้งาน

- [Unix systems](#unix-systems)
  * [Bash](#bash)
  * [Zsh](#zsh)
  * [fish](#fish)
- [Windows](#windows)

# Unix systems

โดยทั่วไปเมื่อติดตั้ง Golang ในระบบ Unix จะถูกกำหนดไว้ที่ `$HOME/go` เพื่อเป็นค่าเริ่มต้น

## Bash

Edit your `~/.bash_profile` to add the following line:
```bash
export GOPATH=$HOME/go
```

Save and exit your editor. Then, source your `~/.bash_profile`.
```bash
source ~/.bash_profile
```

> Note: Set the GOBIN path to generate a binary file when `go install` is run.
> ```bash
> export GOBIN=$HOME/go/bin
> ```

## Zsh

Edit your `~/.zshrc` file to add the following line:

```bash
export GOPATH=$HOME/go
```
Save and exit your editor. Then, source your `~/.zshrc`.
```bash
$ source ~/.zshrc
```

## fish

```bash
set -x -U GOPATH $HOME/go
```
> The `-x` is used to specify that this variable should be exported
> and the `-U` makes this a universal variable, available to all sessions and
> persistent

To set the GOBIN path:

```bash
set -x -U GOBIN $GOPATH/bin
```

# Windows

Your workspace can be located wherever you like,
but we'll use `C:\go-work` in this example.

__NOTE:__ that `GOPATH` must not be the same path as your Go installation.

* Create folder at `C:\go-work`.
* Right click on "Start" and click on "Control Panel". Select "System and Security", then click on "System".
* From the menu on the left, select the "Advanced systems settings".
* Click the "Environment Variables" button at the bottom.
* Click "New" from the "User variables" section.
* Type `GOPATH` into the "Variable name" field.
* Type `C:\go-work` into the "Variable value" field.
* Click OK.

## Windows 10
There is a faster way to edit `Environment Variables` with search
* Left click on "Search" and type `env` or `environment`. select `Edit environment variables for your account`
* and follow step above

...