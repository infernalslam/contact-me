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
  * [Fish](#fish)
- [Windows](#windows)

# Unix systems

โดยทั่วไปเมื่อติดตั้ง Golang ในระบบ Unix จะถูกกำหนดไว้ที่ `$HOME/go` เพื่อเป็นค่าเริ่มต้น โดยเรามสามารถเซ็ทไว้เพื่อความสะดวกในการทำงานอย่างอื่นได้ในอนาคต

## Bash

เข้าไปแก้ไขไฟล์ `~/.bash_profile` เเละเพิ่มคำสั่งทางด้านหลังลงไป

```bash
export GOPATH=$HOME/go
```

บันทึกเเล้วทำการรันคำสั่ง source ที่ไฟล์  `~/.bash_profile` 
```bash
source ~/.bash_profile
```

> หมายเหตุ: การเซ็ท path อย่าลืมเช็ท GOBIN PATH ในกรณีที่ต้องการ generate a binary เมื่อรัน `go install` 
> ```bash
> export GOBIN=$HOME/go/bin
> ```

## Zsh
เข้าไปแก้ไขไฟล์ `~/.zshrc` เเละเพิ่มคำสั่งทางด้านหลังลงไป

```bash
export GOPATH=$HOME/go
```
บันทึกเเล้วทำการรันคำสั่ง source ที่ไฟล์  `~/.zshrc` 

```bash
$ source ~/.zshrc
```

## Fish

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

คุณสามารถติดตั้ง Golang ได้ทุกที่ที่คุณต้องการ
แต่เราจะใช้ `C: \ go-work` ในตัวอย่างนี้


__NOTE:__ `GOPATH` ต้องไม่เป็น PATH เดียวกันกับการติดตั้ง Go ของคุณ

* สร้างโฟร์เดอร์ที่  `C:\go-work`.
* คลิกขวาที่ปุ่ม "Start" เเละคลิกเลือก "Control Panel". เลือก "System and Security", หลังจากนั้นคลิก "System".
* จะมีเมนูปรากฏบนมุมบนซ้ายมือ , เลือกไปที่ "Advanced systems settings".
* คลิกที่ "Environment Variables" ที่อยู่ข้างล่าง.
* คลิก "New" เเละเลือก "User variables" .
* สร้าง Type `GOPATH` ที่ช่อง "Variable name".
* สร้าง Type `C:\go-work` ที่ช่อง "Variable value".
* คลิก OK.
